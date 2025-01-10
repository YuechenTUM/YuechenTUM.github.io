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
  <div class="carousel" style="position: relative; width: 100%; margin: 0 auto; overflow: hidden;">
    <div class="carousel-inner" style="display: flex; transition: transform 0.5s ease;">
      <!-- 图片 1 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div style="display: block; width: 100%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk2.png" alt="Nuuk Image 1" style="display: block; width: 100%; height: auto;" oncontextmenu="return false;" draggable="false" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 1 Description</small></p>
        </div>
      </div>
      <!-- 图片 2 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div style="display: block; width: 100%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk4.png" alt="Nuuk Image 2" style="display: block; width: 100%; height: auto;" oncontextmenu="return false;" draggable="false" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 2 Description</small></p>
        </div>
      </div>
      <!-- 图片 3 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div style="display: block; width: 100%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk5.png" alt="Nuuk Image 3" style="display: block; width: 100%; height: auto;" oncontextmenu="return false;" draggable="false" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 3 Description</small></p>
        </div>
      </div>
    </div>
    <!-- 翻页按钮 -->
    <button class="carousel-control-prev" onclick="prevSlide()" style="position: absolute; top: 50%; left: 10px; transform: translateY(-50%); background: rgba(0, 0, 0, 0.5); color: white; border: none; padding: 10px; cursor: pointer;">&#10094;</button>
    <button class="carousel-control-next" onclick="nextSlide()" style="position: absolute; top: 50%; right: 10px; transform: translateY(-50%); background: rgba(0, 0, 0, 0.5); color: white; border: none; padding: 10px; cursor: pointer;">&#10095;</button>
  </div>
</div>

<script>
  let currentIndex = 0;
  let startX = 0;
  let isDragging = false;

  const carouselInner = document.querySelector('.carousel-inner');

  // 轮播逻辑
  function showSlide(index) {
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

  // 拖动功能（鼠标设备）
  carouselInner.addEventListener('mousedown', (e) => {
    startX = e.clientX;
    isDragging = true;
  });

  carouselInner.addEventListener('mousemove', (e) => {
    if (!isDragging) return;
    const currentX = e.clientX;
    const diffX = startX - currentX;
    if (Math.abs(diffX) > 50) {
      if (diffX > 0) {
        nextSlide();
      } else {
        prevSlide();
      }
      isDragging = false;
    }
  });

  carouselInner.addEventListener('mouseup', () => {
    isDragging = false;
  });

  carouselInner.addEventListener('mouseleave', () => {
    isDragging = false;
  });
</script>

<!-- 仅在图片上禁用右键菜单 -->
<script>
  document.querySelectorAll('img').forEach(img => {
    img.addEventListener('contextmenu', function (e) {
      e.preventDefault(); // 阻止默认右键菜单
    });
  });
</script>

<!-- 监听触摸事件，阻止移动设备上长按触发的下载菜单 -->
<script>
  document.querySelectorAll('img').forEach(img => {
    img.addEventListener('touchstart', function (e) {
      if (e.touches.length === 1) {
        e.preventDefault(); // 阻止触摸行为
      }
    });
  });
</script>
