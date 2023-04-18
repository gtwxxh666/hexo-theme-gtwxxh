---
title: Acrylic主题文档（1.开始）
tags:
  - Acrylic
categories: 教程
description: Acrylic主题使用教程
top_group_index: 1
cover: 'https://cdn.staticaly.com/gh/gtwxxh666/pic@main/1/641fcf22d6666.jpg'
abbrlink: 1b90
date: 2023-04-05 11:24:09
---

![](https://cdn.staticaly.com/gh/gtwxxh666/pic@main/1/hhis5p.jpg)

一些变量解释：

| 变量         | 解释       |
| ------------ | ---------- |
| [blog-root]  | 博客根目录 |
| [theme-root] | 主题根目录 |

# 安装

> hexo-theme-Acrylic 是基于 hexo-theme-butterfly 的基础上进行开发的

{% tabs test4 %}
<!-- tab Github -->

稳定版本

```shell
git clone -b main https://github.com/hexo-theme-Acrylic/hexo-theme-Acrylic.git themes/Acrylic
```

最新版本DEV

```shell
git clone -b dev https://github.com/hexo-theme-Acrylic/hexo-theme-Acrylic.git themes/Acrylic
```

<!-- endtab -->

<!-- tab Gitee -->
**未开发**
<!-- endtab -->

<!-- tab NPM -->
**未开发**
<!-- endtab -->
{% endtabs %}

# 应用

在Hexo配置文件，修改```theme```为```Acrylic```

**区分大小写**

```yaml
theme: Acrylic
```

还要安装插件

```shell
npm install hexo-renderer-pug hexo-renderer-stylus --save
```

# 推荐配置

## MacOS/Linux

在```[blog-root]```里运行：

```shell
cp -rf ./themes/Acrylic/_config.yml ./_config.Acrylic.yml
```

## Windows

复制```[theme-root]```里的_config.yml文件，到```[blog-root]```里

更名为_config.Acrylic.yml

![图片](https://img.gtwxxh.cn/i/2023/04/05/ivn11b.webp)
