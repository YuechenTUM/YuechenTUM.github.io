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

<p>
  Sisimiut lies roughly 320 kilometres north of the capital, Nuuk, and about 75 kilometres north of the Arctic Circle.<sup><a href="https://archive.org/details/greenlandarcticl0000etai/page/8/mode/2up" style="text-decoration: none;">[1]</a></sup> Its name, drawn from the Greenlandic words sisi, meaning "fox den," and miut, meaning "those who live in,"<sup><a href="https://ordbog.gl/2018-kal-eng/#e14271" style="text-decoration: none;">[2]</a></sup> conjures an image of resilient people who have carved out a life in this stark and untamed expanse, and fostering an intimate bond with the natures. Formerly known as Holsteinsborg—a name after Johann Ludwig Holstein that carries the memory of its colonial past.<sup><a href="https://da.wikipedia.org/wiki/Sisimiut" style="text-decoration: none;">[3]</a></sup>
</p>

<!-- 轮播图 -->
<div class="carousel" style="position: relative; width: 100%; margin: 0 auto; overflow: hidden;">
  <div class="carousel-inner" style="display: flex; transition: transform 0.5s ease;">
    <!-- 图片 1 -->
    <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
      <img src="./assets/img/posts/Nuuk/nuuk2.png" alt="Nuuk Image 1" style="width: 100%; height: auto;">
      <p style="text-align: center; margin: 10px 0 0;"><small>Nuuk Image 1 Description</small></p>
    </div>
    <!-- 图片 2 -->
    <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
      <img src="./assets/img/posts/Nuuk/nuuk4.png" alt="Nuuk Image 2" style="width: 100%; height: auto;">
      <p style="text-align: center; margin: 10px 0 0;"><small>Nuuk Image 2 Description</small></p>
    </div>
    <!-- 图片 3 -->
    <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
      <img src="./assets/img/posts/Nuuk/nuuk5.png" alt="Nuuk Image 3" style="width: 100%; height: auto;">
      <p style="text-align: center; margin: 10px 0 0;"><small>Nuuk Image 3 Description</small></p>
    </div>
  </div>
  <!-- 翻页按钮 -->
  <button class="carousel-control-prev" onclick="prevSlide()" style="position: absolute; top: 50%; left: 10px; transform: translateY(-50%); background: rgba(0, 0, 0, 0.5); color: white; border: none; padding: 10px; cursor: pointer;">&#10094;</button>
  <button class="carousel-control-next" onclick="nextSlide()" style="position: absolute; top: 50%; right: 10px; transform: translateY(-50%); background: rgba(0, 0, 0, 0.5); color: white; border: none; padding: 10px; cursor: pointer;">&#10095;</button>
</div>

<!-- 轮播图功能脚本 -->
<script>
  let currentIndex = 0;
  const carouselInner = document.querySelector('.carousel-inner');
  const totalItems = document.querySelectorAll('.carousel-item').length;

  function prevSlide() {
    currentIndex = (currentIndex > 0) ? currentIndex - 1 : totalItems - 1;
    updateCarousel();
  }

  function nextSlide() {
    currentIndex = (currentIndex < totalItems - 1) ? currentIndex + 1 : 0;
    updateCarousel();
  }

  function updateCarousel() {
    const offset = -currentIndex * 100;
    carouselInner.style.transform = `translateX(${offset}%)`;
  }
</script>

<!-- 禁止图片右键菜单和长按下载 -->
<script>
  document.querySelectorAll('img').forEach(img => {
    // 禁用右键菜单
    img.addEventListener('contextmenu', (e) => e.preventDefault());

    // 禁用长按菜单（兼容 iOS）
    img.addEventListener('touchstart', (e) => e.preventDefault(), { passive: false });
    img.addEventListener('touchend', (e) => e.preventDefault(), { passive: false });

    // 禁用图片的指针事件
    img.style.pointerEvents = 'none';
  });
</script>

<!-- 禁止用户在页面中选择文本 -->
<style>
  body {
    -webkit-user-select: none; /* Safari 和 iOS */
    -moz-user-select: none;    /* Firefox */
    -ms-user-select: none;     /* IE 10+ */
    user-select: none;         /* 现代浏览器 */
  }
</style>
