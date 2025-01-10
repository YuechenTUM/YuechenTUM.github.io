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
        <div style="display: block; width: 90%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk2.png" alt="Nuuk Image 1" style="display: block; width: 100%; height: auto;" oncontextmenu="return false;" draggable="false" style="pointer-events: none;" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 1 Description</small></p>
        </div>
      </div>
      <!-- 图片 2 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div style="display: block; width: 90%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk4.png" alt="Nuuk Image 2" style="display: block; width: 100%; height: auto;" oncontextmenu="return false;" draggable="false" style="pointer-events: none;" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 2 Description</small></p>
        </div>
      </div>
      <!-- 图片 3 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div style="display: block; width: 90%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk5.png" alt="Nuuk Image 3" style="display: block; width: 100%; height: auto;" oncontextmenu="return false;" draggable="false" style="pointer-events: none;" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 3 Description</small></p>
        </div>
      </div>
    </div>
    <!-- 指示器 -->
    <div class="carousel-indicators" style="position: absolute; bottom: 10px; left: 50%; transform: translateX(-50%); display: flex; gap: 5px; z-index: 10;">
      <span class="indicator" data-index="0" style="width: 20px; height: 3px; background-color: rgba(255, 255, 255, 0.5); cursor: pointer;"></span>
      <span class="indicator" data-index="1" style="width: 20px; height: 3px; background-color: rgba(255, 255, 255, 0.5); cursor: pointer;"></span>
      <span class="indicator" data-index="2" style="width: 20px; height: 3px; background-color: rgba(255, 255, 255, 0.5); cursor: pointer;"></span>
    </div>
  </div>
</div>

<script>
  let currentIndex = 0;
  const carouselInner = document.querySelector('.carousel-inner');
  const indicators = document.querySelectorAll('.indicator');

  // 显示指定索引的图片
  function showSlide(index) {
    const totalItems = document.querySelectorAll('.carousel-item').length;
    if (index >= totalItems) currentIndex = 0;
    if (index < 0) currentIndex = totalItems - 1;
    carouselInner.style.transform = `translateX(-${currentIndex * 100}%)`;
    updateIndicators();
  }

  // 更新指示器状态
  function updateIndicators() {
    indicators.forEach((indicator, i) => {
      if (i === currentIndex) {
        indicator.style.backgroundColor = 'rgba(255, 255, 255, 1)'; // 激活状态
      } else {
        indicator.style.backgroundColor = 'rgba(255, 255, 255, 0.5)'; // 默认状态
      }
    });
  }

  // 下一张
  function nextSlide() {
    currentIndex++;
    showSlide(currentIndex);
  }

  // 点击指示器跳转
  indicators.forEach((indicator) => {
    indicator.addEventListener('click', () => {
      currentIndex = parseInt(indicator.getAttribute('data-index'));
      showSlide(currentIndex);
    });
  });
  
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
  document.addEventListener('touchstart', function (e) {
    if (e.target.tagName === 'IMG') {
      e.preventDefault(); // 禁止触摸开始
    }
  });

  document.addEventListener('touchmove', function (e) {
    if (e.target.tagName === 'IMG') {
      e.preventDefault(); // 禁止触摸移动
    }
  });

  document.addEventListener('touchend', function (e) {
    if (e.target.tagName === 'IMG') {
      e.preventDefault(); // 禁止触摸结束
    }
  });
</script>

<!-- 禁止用户在页面中选择文本和图片 -->
<style>
  body, img {
    -webkit-user-select: none; /* 禁止 Safari 和 iOS 选择 */
    user-select: none;         /* 禁止现代浏览器选择 */
  }
  img {
    pointer-events: none;      /* 禁用指针事件，防止复制图片 */
  }
</style>
