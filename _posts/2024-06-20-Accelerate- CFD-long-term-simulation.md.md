---
layout: post
read_time: true
show_date: true
title: Can CFD simulations be accelerated?
date: 2024-06-20
img: posts/20240620/HPC.jpg
img_caption: "Photo by Bent Bach"
tags: [CFD, High-performance computing, Ansys fluent, 3D model]
category: opinion
author: Yueechen
description: "When using the commercial software Fluent for simulation, in addition to focusing on the results, time cost is also a significant factor. So can long-term CFD transient simulations be accelerated?"
toc: yes
---
## Background

I recently completed my master's thesis, which focused on the CFD simulation of pit thermal storage. Initially, I collaborated with a Chinese university to develop a dedicated C++ program for fundamental acceleration but ended up using Ansys Fluent to simulate a 3D model for a year for various reasons in the remaining three months. This blog will explore ways to accelerate the simulation through considerations such as employing HPC, CPU selection, I/O performance, and case scaling.

## High performance computing

![The High performance cluster](./assets/img/posts/20240620/HPC_2.webp) <small>The High performance cluster - [Picture Source](https://medium.com/quantonation/a-beginners-guide-to-high-performance-computing-ae70246a7af)</small>

High-performance computing uses tens of thousands to millions of processors or processor cores for parallel computing, which has the advantages of being more stable when performing heavy numerical computing tasks, and its running speed is usually much faster than the fastest laptop or server system.

<tweet>HPC is a technology that uses clusters of powerful processors that work in parallel to process massive, multidimensional data sets and solve complex problems at extremely high speeds.<a href="https://www.ibm.com/topics/hpc">[1]</a></tweet>

 [DTU Computing Center](https://www.hpc.dtu.dk/) manages the cluster and is open to all students and employees [33]. The facility runs on the Linux  system and uses the LSF (Load Sharing Facility) platform to schedule and manage jobs in the task pool. The following script is a template for the submission of a parallel shared memory job, running on one single node.
 
```bash
#!/bin/sh
# embedded options to bsub - start with #BSUB
#BSUB -J Ansys_FLUENT_Case 
#BSUB -q hpc
#BSUB -W 04:00
#BSUB -R "rusage[mem=2GB]"
#BSUB -n 4
#BSUB -R "span[hosts=1]"
# -- user email address --
##BSUB -u your_email_address
# -- at start --
#BSUB -B
# -- at completion --
#BSUB -N
# --Specify the output and error file. %J is the job-id --
# --  -o and -e mean append, -oo and -eo mean overwrite -- 
#BSUB -oo fluent_local_intel_%J.out
#BSUB -eo fluent_local_intel_%J.err

# Set the environment variable to fix ssh issue
export SSH_SPAWN=0
# Set the environment variable to fix IntelMPI issue (fluent v18+)
export I_MPI_SHM_LMT=shm
#example of ansys command line call
/appl/ansys/2023R2/v232/fluent/bin/fluent 3ddp -g -t$LSB_DJOB_NUMPROC -i instruction.journal -mpi=intel > fluent_run.out
```
It is also possible to use distributed storage to place tasks on different computing nodes and use GPU resources for computing. Make the corresponding modifications to the above script.

## CPU Models and I/O Performance

DTU Computing Center provides a range of CPU models to choose from. According to an Ansys [White paper](https://www.ansys.com/resource-center/white-paper/how-to-select-the-best-processor-and-hpc-system-for-your-ansys-workloads), Fluent generally benefits more from higher memory capacity and bandwidth than from higher core counts and frequencies [35]. The results show that the cpu XeonGold 6342 exhibits the fastest performance, with an average per-iteration time that is approximately 20.33% faster than the cpu XeonGold 6126. 

![CPU diagram](./assets/img/posts/20240620/CPU.jpg) <small>The CPU diagram - [Picture Source](https://greenluffa.com/jp/intel-%E7%AC%AC-12-%E4%B8%96%E4%BB%A3-alder-lake-cpu-%E3%81%AE%E3%82%BD%E3%83%BC%E3%82%B9-%E3%82%B3%E3%83%BC%E3%83%89%E3%81%8C%E3%83%8F%E3%83%83%E3%82%AD%E3%83%B3%E3%82%B0%E5%BE%8C%E3%81%AB%E6%B5%81/)</small>

In addition, communication throughput is critical for large clusters, especially when dealing with transient models. In addition, I/O performance plays a crucial role. However, students often lack direct access to monitor system I/O activity, which makes it challenging to evaluate the performance of I/O performance. Through a rough test, the model with a reporting interval of 600 seconds takes approximately 28.65% longer than the model without reporting output. And The total wall clock time with a reporting output interval of 1200 seconds is comparable to the wall clock time without any output.

## Fluent version

At the same time, it is necessary to consider the impact of different versions of Ansys Fluent on computing efficiency. As Ansys continues to develop and optimize the underlying code, the computing speed is expected to increase in theory. Three Fluent versions, 202R1, 2021R1, and 2022R1, were tested. Versions 2023 and 2024 have undergone major changes, so these two versions were not tested. In the tests of these three versions in the same environment, in addition to testing single-thread serial computing, 2 or 4-thread parallel computing was also tested. In serial computing, the 2021R1 version was 7.479% slower than the 2020R1 version unexpected, and the 2022R1 version was 10.20% slower. In four-thread parallel computing, the 2021R1 version was 7.94% slower than the 2020R1 version, and the 2022R1 version was 7.597% slower than the 2020R1 version.

## Parallel Computing and Scalability

Additionally, when performing parallel computing in high-performance computing, scale testing with different settings for each case is essential. In general, it is widely believed that using more threads will reduce the total wall clock time. However, increasing the number of threads does not always improve efficiency. Even on a single host, there is a critical threshold: beyond a certain number of threads, the speedup effect stagnates or even decreases. 

<div style="display: flex; justify-content: space-around;">
  <img src="/assets/img/posts/20240620/Gen_DSpeedupDN_amdahl.png" alt="Gen DSpeedupDN Amdahl" style="width: 50%;">
  <img src="/assets/img/posts/20240620/Gen_Speedup_amdahl.png" alt="Gen Speedup Amdahl" style="width: 50%;">
</div>

This is because the overhead of information exchange between threads increases, and the more threads, the greater the overhead, which offsets the benefits of parallelism. In the case of using distributed memory technology, multiple nodes are used, resulting in greater communication overhead. The benefits can only be obtained when the model scale is large enough to require the use of distributed storage technology; otherwise, the increased communication overhead will extend the total wall clock time.


