---
title: Hexo部署到服务器
categories:
  - 教程
cover: 'https://npm.elemecdn.com/saiodgm-api@1.0.1/randomimg-my/7.webp'
tags:
  - 服务器
ai: true
description: 总结Hexo部署服务器方法
abbrlink: '5951'
date: 2023-04-22 20:17:57
---

{% link CSDN-将 Hexo 部署/迁移到腾讯云轻量服务器,https://blog.csdn.net/qq_41467882/article/details/124861190 , https://blog.csdn.net/qq_41467882/article/details/124861190 %}

# 前言

> 本教程记录📝Hexo博客部署服务器的方法，脱离Github Pages。可参考

# 准备

确保你的Hexo能正常渲染访问，本地环境正常安装（如`Git`，`Node.js`）。还得有一台服务器。

最好安装宝塔面板，或者1Panel，又或者OneinStack

{% folding 安装环境 %}

宝塔面板：本站有

1Panel：https://1panel.cn/docs/installation/online_installation/

OneinStack：https://oneinstack.com/auto/

{% endfolding %}

# 开始！

登录服务器后，安装Git

```shell
apt install git ## Ubuntu/Debian
yum install git ## CentOS
```

创建Git账户

```shell
adduser git
chmod 740 /etc/sudoers
vim /etc/sudoers
```

