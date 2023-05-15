---
title: 分类
date: 2023-03-29 20:26:31
aside: true
---
{% raw %}

<style>
  #libCategories .card-wrap:hover .card-info:after {
    width: 300%;
  }
</style>
<link rel="stylesheet" type="text/css" href="https://npm.elemecdn.com/js-heo@1.0.11/3dCard/no3d.css">

<div id='libCategories'>
<div id="lib-cards" class="container">

<a href='javascript:void(0);' onClick='pjax.loadUrl("/categories/教程/")'>
<card data-image="https://npm.elemecdn.com/saiodgm-api@1.0.1/randomimg-my/25.webp">
<h1 slot="header">教程</h1>
<p slot="content">学习之路</p>
</card>
</a>

<a href='javascript:void(0);' onClick='pjax.loadUrl("/categories/杂项/")'>
  <card data-image="https://npm.elemecdn.com/saiodgm-api@1.0.1/randomimg-my/27.webp">
    <h1 slot="header">杂项</h1>
    <p slot="content">杂乱</p>
  </card>
</a>

<a href='javascript:void(0);' onClick='pjax.loadUrl("/categories/生活日常/")'>
  <card data-image="https://npm.elemecdn.com/saiodgm-api@1.0.1/randomimg-my/28.webp">
    <h1 slot="header">生活</h1>
    <p slot="content">经历的有趣事。</p>
  </card>
</a>

<a href='javascript:void(0);' onClick='pjax.loadUrl("/categories/演示/")'>
  <card data-image="https://cdn.staticaly.com/gh/gtwxxh666/pic@main/1/home_bg.webp">
    <h1 slot="header">演示</h1>
    <p slot="content">......</p>
  </card>
</a>

</div>
</div>

<script src='https://lf6-cdn-tos.bytecdntp.com/cdn/expire-1-M/vue/2.6.14/vue.min.js' data-pjax></script>

<script type="text/javascript" src="https://npm.elemecdn.com/anzhiyu-theme-static@1.0.7/no3d/no3d.js" data-pjax></script>

{% endraw %}