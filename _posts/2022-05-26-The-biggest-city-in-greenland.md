---
layout: post
read_time: true
show_date: true
title: The biggest city in greenland
date: 2023-02-10
img: posts/Nuuk/nuuk_homepage.png
tags: [travelogue,greenland]
category: opinion
author: Yueechen
description: Root in Sisimiut and embrace the enchanting polar night and day, bask in the ethereal glow of the northern lights.
---
<blockquote style="font-family: 'Times New Roman', Times, serif; font-style: italic; font-size: 20px;">
Who would have thought that life's winding paths would lead me here, to dwell amidst the breathtaking beauty of this untouched wilderness?
</blockquote>

<p>Sisimiut lies roughly 320 kilometres north of the capital, Nuuk, and about 75 kilometres north of the Arctic Circle.<sup><a href="https://archive.org/details/greenlandarcticl0000etai/page/8/mode/2up" style="text-decoration: none;">[1]</a></sup> Its name, drawn from the Greenlandic words sisi, meaning "fox den," and miut, meaning "those who live in,"<sup><a href="https://ordbog.gl/2018-kal-eng/#e14271" style="text-decoration: none;">[2]</a></sup> conjures an image of resilient people who have carved out a life in this stark and untamed expanse, and fostering an intimate bond with the natures. Formerly known as Holsteinsborg—a name after Johann Ludwig Holstein that carries the memory of its colonial past.<sup><a href="https://da.wikipedia.org/wiki/Sisimiut" style="text-decoration: none;">[3]</a></sup></p>

<div style="text-align: center;">
  <div class="carousel" style="position: relative; width: 80%; margin: 0 auto; overflow: hidden;">
    <div class="carousel-inner" style="display: flex; transition: transform 0.5s ease;">
      <!-- 动态加载的图片容器 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div id="image1" style="width: 100%; height: auto;"></div>
        <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 1 Description</small></p>
      </div>
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div id="image2" style="width: 100%; height: auto;"></div>
        <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 2 Description</small></p>
      </div>
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div id="image3" style="width: 100%; height: auto;"></div>
        <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 3 Description</small></p>
      </div>
    </div>
    <!-- 翻页按钮 -->
    <button class="carousel-control-prev" onclick="prevSlide()" style="position: absolute; top: 50%; left: 10px; transform: translateY(-50%); background: rgba(0, 0, 0, 0.5); color: white; border: none; padding: 10px; cursor: pointer;">&#10094;</button>
    <button class="carousel-control-next" onclick="nextSlide()" style="position: absolute; top: 50%; right: 10px; transform: translateY(-50%); background: rgba(0, 0, 0, 0.5); color: white; border: none; padding: 10px; cursor: pointer;">&#10095;</button>
  </div>
</div>

<script>
  // 动态加载图片
  const images = [
    { id: 'image1', src: './assets/img/posts/Nuuk/nuuk1.png' },
    { id: 'image2', src: './assets/img/posts/Nuuk/nuuk2.png' },
    { id: 'image3', src: './assets/img/posts/Nuuk/nuuk3.png' }
  ];

  images.forEach(image => {
    const img = new Image();
    img.src = image.src;
    img.style.width = '100%';
    img.style.height = 'auto';
    document.getElementById(image.id).appendChild(img);
  });

  // 轮播逻辑
  let currentIndex = 0;

  function showSlide(index) {
    const carouselInner = document.querySelector('.carousel-inner');
    const totalItems = document.querySelectorAll('.carousel-item').length;
    if (index >= totalItems) currentIndex = 0;
    if (index < 0) currentIndex = totalItems - 1;
    carouselInner.style.transform = `translateX(-${currentIndex * 100}%)`;
  }

  function nextSlide() {
    currentIndex++;
    showSlide(currentIndex);
  }

  function prevSlide() {
    currentIndex--;
    showSlide(currentIndex);
  }
</script>

<!-- 仅在图片上禁用右键菜单 -->
<script>
  document.querySelectorAll('img').forEach(img => {
    img.addEventListener('contextmenu', function (e) {
      e.preventDefault(); // 阻止默认右键菜单
    });
  });
</script>
