---
layout: post
read_time: true
show_date: true
title: "Can long-term CFD transient simulations be accelerated?"
date: 2024-06-20
img: posts/20240620/Dronn-p.jpg
img_caption: "Photo by Bent Bach"
tags: [CFD, High-performance cluster, Ansys fluent, 3D model]
category: opinion
author: Yueechen
description: "When using the commercial software Fluent for simulation, in addition to focusing on the results, time cost is also a significant factor. So can long-term CFD transient simulations be accelerated?"
---
Recently, I finished writing my master's thesis. During these six months, time has always been an important factor that bothered me. In the first three months, I actively cooperated with a Chinese university to try to develop a program specifically for pit thermal storage simulation in C++ to fundamentally accelerate the simulation and phase in the development of the information exchange code for the universal grid of the two-dimensional interface. But for various reasons, I eventually had to use the commercial software Ansys Fluent to simulate a three-dimensional model for a year, and how to speed up became the issue I considered the most in the rest three months.

First of all, high performance computing has to be utlized, because it has become a necessary method to ensure computing efficiency and stability when performing heavy numerical computing tasks. [DTU Computing Center](https://www.hpc.dtu.dk/) manages the cluster and is open to all students and employees [^33]. The facility runs on the Linux  system and uses the LSF (Load Sharing Facility) platform to schedule and manage jobs in the cluster. The following code block shows a brief example of calling CPU resources.

```linux
#BSUB -q hpc
#BSUB -n 32
#BSUB -R span[ptile=16]
#BSUB -R "select[model=XeonGold6342]"
#BSUB -R rusage[mem=4GB]
#BSUB -W 72:00
/xxxx/fluent 3ddp -g -t$LSB_DJOB_NUMPROC -i instruction.journal -mpi=intel -cnf=$LSB_DJOB_RANKFILE > console.out
```
DCC provides a range of CPU models to choose from. According to an Ansys white paper, Fluent generally benefits more from higher memory capacity and bandwidth than from higher core counts and frequencies [35]. The results show that the cpu XeonGold 6342 exhibits the fastest performance, with an average per-iteration time that is approximately 20.33% faster than the cpu XeonGold 6126. In addition, communication throughput is critical for large clusters, especially when dealing with transient models. In addition, I/O performance plays a crucial role. However, students often lack direct access to monitor system I/O activity, which makes it challenging to evaluate the performance of I/O performance. Through a rough test, the model with a reporting interval of 600 seconds takes approximately 28.65% longer than the model without reporting output. And The total wall clock time with a reporting output interval of 1200 seconds is comparable to the wall clock time without any output.


![The next Rembrandt](./assets/img/posts/20210420/post8-rembrandt2.jpg)
<small>[The Next Rembrandt](https://www.jwt.com/en/work/thenextrembrandt) is a computer-generated 3-D–printed painting developed by a facial-recognition algorithm that scanned data from 346 known paintings by the Dutch painter in a process lasting 18 months. The portrait is based on 168,263 fragments from Rembrandt’s works.</small>

