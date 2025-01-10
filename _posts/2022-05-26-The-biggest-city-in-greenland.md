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
        <div class="image-container" style="display: block; width: 100%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk2.png" alt="Nuuk Image 1" style="display: block; width: 100%; height: 100%; object-fit: cover;" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 1 Description</small></p>
        </div>
      </div>
      <!-- 图片 2 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div class="image-container" style="display: block; width: 100%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk4.png" alt="Nuuk Image 2" style="display: block; width: 100%; height: 100%; object-fit: cover;" />
          <p style="text-align: center; margin: 10px 0 0 0;"><small>Nuuk Image 2 Description</small></p>
        </div>
      </div>
      <!-- 图片 3 -->
      <div class="carousel-item" style="min-width: 100%; box-sizing: border-box;">
        <div class="image-container" style="display: block; width: 100%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
          <img src="./assets/img/posts/Nuuk/nuuk5.png" alt="Nuuk Image 3" style="display: block; width: 100%; height: 100%; object-fit: cover;" />
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

<!-- 禁止长按图片触发下载菜单 -->
<script>
  document.addEventListener('contextmenu', function (e) {
    if (e.target.tagName === 'IMG') {
      e.preventDefault(); // 禁止长按菜单
    }
  });
</script>

<!-- 禁止用户在页面中选择文本 -->
<style>
  body {
    -webkit-user-select: none; /* 禁止 Safari 和 iOS 选择 */
    user-select: none;         /* 禁止现代浏览器选择 */
  }
</style>

<script>
  let currentIndex = 0;
  const carouselInner = document.querySelector('.carousel-inner');
  const indicators = document.querySelectorAll('.indicator');
  const carouselItems = document.querySelectorAll('.carousel-item');
  const imageContainers = document.querySelectorAll('.image-container');

  // 动态调整图片容器大小
  function adjustImageSize() {
    let maxHeight = 0;

    // 找到所有图片容器中的最大高度
    imageContainers.forEach(container => {
      if (container.clientHeight > maxHeight) {
        maxHeight = container.clientHeight;
      }
    });

    // 将所有图片容器的高度设置为最大高度
    imageContainers.forEach(container => {
      container.style.height = `${maxHeight}px`;
    });
  }

  // 显示指定索引的图片
  function showSlide(index) {
    const totalItems = carouselItems.length;
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

  // 上一张
  function prevSlide() {
    currentIndex--;
    showSlide(currentIndex);
  }

  // 点击指示器跳转
  indicators.forEach((indicator) => {
    indicator.addEventListener('click', () => {
      currentIndex = parseInt(indicator.getAttribute('data-index'));
      showSlide(currentIndex);
    });
  });

  // 初始化
  adjustImageSize(); // 动态调整图片大小
  updateIndicators();

  // 监听窗口大小变化
  window.addEventListener('resize', adjustImageSize);

  // 触摸滑动功能
  let startX = 0;
  let isDragging = false;

  carouselInner.addEventListener('touchstart', (e) => {
    startX = e.touches[0].clientX; // 记录触摸起始位置
    isDragging = true;
  });

  carouselInner.addEventListener('touchmove', (e) => {
    if (!isDragging) return;
    const currentX = e.touches[0].clientX; // 获取当前触摸位置
    const diffX = startX - currentX; // 计算滑动距离

    // 如果滑动距离超过 50px，切换图片
    if (Math.abs(diffX) > 50) {
      if (diffX > 0) {
        nextSlide(); // 向右滑动，切换到下一张
      } else {
        prevSlide(); // 向左滑动，切换到上一张
      }
      isDragging = false; // 结束拖动
    }
  });

  carouselInner.addEventListener('touchend', () => {
    isDragging = false; // 结束拖动
  });

<!-- 仅在图片上禁用右键菜单 -->
<script>
  document.querySelectorAll('img').forEach(img => {
    img.addEventListener('contextmenu', function (e) {
      e.preventDefault(); // 阻止默认右键菜单
    });
  });
</script>
