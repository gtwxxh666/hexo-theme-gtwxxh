---
title: Acrylic主题文档（2-配置)
tags:
  - Acrylic
categories: 教程
description: Acrylic主题使用教程
top_group_index: 5
cover: 'https://cdn.staticaly.com/gh/gtwxxh666/pic@main/1/641fcf22d6666.jpg'
abbrlink: 76f9
date: 2023-04-05 11:46:00
---

一些变量解释：

| 变量         | 解释       |
| ------------ | ---------- |
| [blog-root]  | 博客根目录 |
| [theme-root] | 主题根目录 |

# 基本认识

``Front-matter`` 为 页面或文章顶部配置与使用，此处不再赘述，具体配置请参考[Butterfly](https://butterfly.js.org/posts/dc584b87/)

本主题添加了以下内容（仅支持文章）

```
---
title: Hello World
swiper_index: 1
---
```

``swiper_index``是指首页上方右侧显示的文章。

如果设置的文章小于等于3。那是从上往下，从右边到左边

![](https://img.gtwxxh.cn/i/2023/04/05/k62xe1-2.webp)

反之，如果设置的文章大于3，那从上到下，从左往右。

![](https://img.gtwxxh.cn/i/2023/04/05/k73r4q-2.webp)

{% tip info %}如果第2行设置没用达到3，那么是从右往左的{% endtip %}

只有在主题配置文件里，将首页hometop里的topgroup。

框选的class设置post/both才会显示文章

![](https://img.gtwxxh.cn/i/2023/04/05/kbritz-2.webp)

# 导航栏

在主题配置文件里有

![](https://img.gtwxxh.cn/i/2023/04/05/kceokt-2.webp)

其中，nav里的left_groups。是指以下内容

![](https://img.gtwxxh.cn/i/2023/04/05/kczdau-2.webp)

class为out是在新标签页打开链接

menu是指中间那几个部分

格式为：

```yaml
文字: 链接 || 图标
```

如果父菜单不想跳转，链接可以设置成``#``

![](https://img.gtwxxh.cn/i/2023/04/05/kdn9gs-2.webp)

right_button就是右边的

+ travelling：开往项目
+ random：随机文章
+ console：设置界面

![](https://img.gtwxxh.cn/i/2023/04/05/kf07uu-2.webp)

# 首页顶部栏

在主题配置文件有

![](https://img.gtwxxh.cn/i/2023/04/05/khrhrp-2.webp)

显示部分如下图

![](https://img.gtwxxh.cn/i/2023/04/05/kifrac-2.webp)

+ Banner里的class：creativity是指技能点，people为人潮汹涌
+ 分类里的颜色可以自定义，填写HEX或者CSS变量
+ 右侧文章前面的``基本认识``里有讲

# 即刻短文

首先，在``[blog-root]``里，执行以下指令

```shell
hexo new page essay
```

在``[blog-root]/source/essay/index.md``里，写：

```markdown
---
title: 即刻短文
date: 2020-07-22 22:06:17
comments: true
aside: false
type: essay
---

```

创建``[blog-root]/source/_data/essay.yml``

写入：

```yaml
- class_name: 即刻短文
  essay_list:
    - content: 即刻短文用上了木木发的waterfall的js，瀑布流真令人愉悦
      date: 2022-08-12
    - content: iOS16现在感觉已经很稳定了，bug比较少，令人讨厌的就是一个是切换横竖屏抖音和b站都有点问题，然后就是软件请求剪贴板弹窗真的烦
      date: 2022-08-12
    - content: 现在即刻短文已经纯本地化部署完成，不再依赖任何第三方服务了
      date: 2022-08-12
    - content: 在整理转载文章的时候发现很多文章原文都无法访问了，所以本地保存网页是非常重要的
      date: 2022-08-05T06:08:54.978Z
    - content: adguardhome真的不能设置太久的缓存时间，否则非常容易卡和无响应。然后就是注意添加白名单
      date: 2022-08-04T10:10:09.984Z

```

# 关于

关于页里的大多数在配置文件中，可以看一下。

{% link 关于本站 | 张洪Heo,张洪Heo,https://blog.zhheo.com/about/ %}

# 搜索

{% tabs test4 %}
<!-- tab Algolia -->

> 记得运行 Hexo cl
>
> 如果你使用 hexo-algoliasearch，请记得配置 fields 参数的 title, permalink 和 content

1. 安装[hexo-algolia](https://github.com/oncletom/hexo-algolia)或者[hexo-algoliasearch](https://github.com/LouisBarranqueiro/hexo-algoliasearch)

2. 按照教程去配置

3. 修改配置文件

   ```yaml
   # 搜索
   # --------------------------------
   # Algolia search
   algolia_search:
     enable: true
     hits:
       per_page: 6
   ```

<!-- endtab -->

<!-- tab 本地搜索 -->

> 记得运行 Hexo cl

1. 安装[hexo-generator-search](https://github.com/wzpan/hexo-generator-search)插件

2. 配置文件

   ```yaml
   # Local search
   local_search:
     enable: true
     preload: false
     CDN:
   ```

<!-- endtab -->

{% endtabs %}

# 字数统计

1. 在``[blog-root]``安装插件``wordcount``

   ```
   npm install hexo-wordcount --save
   ```

2. 配置文件修改

   ```yaml
   # 字数统计
   # 注意安装对应的插件
   wordcount:
     enable: true
     post_wordcount: true
     min2read: true
     total_wordcount: true
   ```

# 底部

在配置文件里有

示例图：

![](https://img.gtwxxh.cn/i/2023/04/05/n64i75-2.webp)

可以根据文字来决定配置文件改的是哪个位置

# 最后

其实，要讲的都讲完了。

这个主题开发才过了一半，Bug还蛮多的。

这里，也祝Acrylic主题越来越好！

