---
title: Acrylic主题文档(三) 进阶配置
ai: true
tags:
  - Acrylic
categories: 教程
description: Acrylic主题使用教程
top_group_index: 6
cover: 'https://cdn.staticaly.com/gh/gtwxxh666/pic@main/1/641fcf22d6666.jpg'
abbrlink: f1d3
date: 2023-05-02 15:24:09
---

一些变量解释：

| 变量         | 解释       |
| ------------ | ---------- |
| [blog-root]  | 博客根目录 |
| [theme-root] | 主题根目录 |

# CSS与JS引入

待填写，这个内容较多，会单独出。

# RSS阅读订阅

运行：

```shell
npm install hexo-generator-feed --save
```

在`_config.yml`里，添加以下内容：

```yaml
# https://github.com/hexojs/hexo-generator-feed
# Feed Atom
feed:
    type: atom
    path: atom.xml
    limit: 20
rss: /atom.xml
```

# 站点地图 SiteMap

运行：

```shell
npm install hexo-generator-sitemap --save
npm install hexo-generator-baidu-sitemap --save-dev
```

在`_config.yml`里，添加以下内容：

```yaml
# Extensions
plugins:
    - hexo-generator-feed
    - hexo-generator-baidu-sitemap
    - hexo-generator-sitemap
 
# https://github.com/hexojs/hexo-generator-sitemap
sitemap:
  path: sitemap.xml
  rel: false
  tags: true
  categories: true

# https://github.com/coneycode/hexo-generator-baidu-sitemap
baidusitemap:
    path: baidusitemap.xml
```

# 文章链接转数字或字母

```shell
npm install hexo-abbrlink --save
```

```yaml
# 文章链接转数字或字母：https://github.com/rozbo/hexo-abbrlink
abbrlink:
	alg: crc16   
	rep: hex
```

# 追番

```shell
npm install hexo-bilibili-bangumi --save
```

```yaml
# 追番插件
# https://github.com/HCLonely/hexo-bilibili-bangumi
bangumi: # 追番设置
  enable: true
  path:
  vmid: 372204786
  title: '追番列表'
  quote: '生命不息，追番不止！'
  show: 1
  lazyload: false
  loading:
  metaColor:
  color:
  webp:
  progress:
  extra_options:
    key: value
cinema: # 追剧设置
  enable: false
  path:
  vmid: 372204786
  title: '追剧列表'
  quote: '生命不息，追剧不止！'
  show: 1
  lazyload: true
  loading:
  metaColor:
  color:
  webp:
  progress:
  extra_options:
    key: value
```

B站里还要修改设置，否则会提示无法获取。

![](https://img.gtwxxh.cn/i/2023/05/6450c7113a8d5.webp)

vmid就是链接里的这一串数字

![](https://img.gtwxxh.cn/i/2023/05/6450c769e0d99.webp)

# iconfont图标引入

详见：

{% link Iconfont Inject,Akilar糖果屋,https://akilar.top/posts/d2ebecef/ %}

# 图片压缩

Acrylic需要很多图片，除了用`gulp-imagemin`来进行压缩，还可以使用在线网站或者图床来进行压缩

## tinypng

一个在线压缩的网站。压缩后的图片也保留了很高的质量，在知乎上很多人推荐，不过免费版有限制。

{% link tinypng,tinypng,https://tinypng.com/%}

![](https://img.gtwxxh.cn/i/2023/05/6450c95aacb1e.webp)

## caesium（推荐）

这是一款开源的软件，支持Windows和macOS，支持批量，无限制

{% link caesium,caesium,https://saerasoft.com/caesium/ %}

![](https://img.gtwxxh.cn/i/2023/05/6450ca68b5251.webp)
