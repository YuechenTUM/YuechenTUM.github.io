---
layout: post
read_time: true
show_date: true
title: {{ site.data[site.lang].welcome }}
date: 2023-02-10
img: posts/Sisimiut/greenland.jpg
tags: [travelogue,greenland]
category: opinion
author: Yueechen
description: {{ site.data[site.lang].description }}
---

<blockquote style="font-family: 'Times New Roman', Times, serif; font-style: italic; font-size: 20px;">
  {{ site.data[site.lang].quote }}
</blockquote>

<p>{{ site.data[site.lang].sisimiut_description }}<sup><a href="https://archive.org/details/greenlandarcticl0000etai/page/8/mode/2up" style="text-decoration: none;">[1]</a></sup> Its name, drawn from the Greenlandic words sisi, meaning "fox den," and miut, meaning "those who live in,"<sup><a href="https://ordbog.gl/2018-kal-eng/#e14271" style="text-decoration: none;">[2]</a></sup> conjures an image of resilient people who have carved out a life in this stark and untamed expanse, and fostering an intimate bond with the natures. Formerly known as Holsteinsborg—a name after Johann Ludwig Holstein that carries the memory of its colonial past.<sup><a href="https://da.wikipedia.org/wiki/Sisimiut" style="text-decoration: none;">[3]</a></sup></p>

<div style="text-align: center;">
  <div style="display: block; width: 80%; padding: 10px; background-color: rgba(0, 0, 0, 0.1); box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); margin: 0 auto;">
    <img src="./assets/img/posts/Sisimiut/Apisseq.jpg" alt="Engineers's house Apisseq" style="display: block; width: 100%; height: auto;">
    <p style="text-align: center; margin: 10px 0 0 0;"><small>Engineers's house Apisseq (Photo by Malik Broberg)</small></p>
  </div>
</div>

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
