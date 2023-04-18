---
title: Acrylic主题文档（3-再配置）
description: Acrylic主题使用教程
tags: Acrylic
categories: 教程
top_group_index: 6
cover: 'https://cdn.staticaly.com/gh/gtwxxh666/pic@main/1/641fcf22d6666.jpg'
abbrlink: aea2
date: 2023-04-08 20:12:32
---

一些变量解释：

| 变量         | 解释       |
| ------------ | ---------- |
| [blog-root]  | 博客根目录 |
| [theme-root] | 主题根目录 |

太6了写完才发现，配置1是新功能，本文才是普通。

# 友情链接配置

在``[blog-root]``里运行以下脚本

```shell
hexo new page link
```

打开``[blog-root]/source/link/index.md``

添加以下内容：

```diff
---
title: 友人帐
date: 2023-03-29 20:30:06
+ type: 'link'
+ aside: false
---
```

其次：创建``[blog-root]/source/_data/link.yml``

输入以下内容：

```yaml
- class_name: 小伙伴
  class_desc: 那些人，那些事
  flink_style: butterfly
  link_list:
    - name: 我不是咕咕鸽
      link: https://blog.laoda.de
      avatar: https://blog.laoda.de/logo
      descr: 服务器折腾不完全指南，定期分享一些好玩的东西，不定期记录生活。
    - name: 清风
      link: https://limh.cc/
      avatar: https://limh.cc/img/avatar.webp
      descr: 人不拼怎知输赢
```

Hexo3连查看效果

# 标签页

