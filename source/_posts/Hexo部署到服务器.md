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
sudo -i
adduser git
chmod 740 /etc/sudoers
vim /etc/sudoers
```

**提醒：Ubuntu/Debian在创建时会要求输入密码，输入即可**

添加`git ALL=(ALL) ALL`

![image-20230507121528547](https://img.gtwxxh.cn/i/2023/05/645725e10f76e.webp)

找一找差不多的地方

改回权限：

```shell
chmod 400 /etc/sudoers
```

## 设置密码

CentOS必须，Ubuntu/Debian跳过！

```shell
sudo passwd git
```

设置的密码看不到，你直接输入就可以了。

## 设置SSH密钥

登录git用户，创建ssh文件夹并设置密钥

```shell
su git
mkdir ~/.ssh
vim ~/.ssh/authorized_keys
```

密钥详见安知鱼：https://anzhiy.cn/posts/ddae.html第9

赋予权限：

```she
chmod 600 /home/git/.ssh/authorized_keys
chmod 700 /home/git/.ssh
```

尝试登录服务器：

在本地终端（cmd）运行

```shell
ssh -v git@SERVER
```

SERVER替换成你的服务器iP

如果没有提示password之类的，就Ok！

如果提示`Are you sure you want to continue connecting (yes/no/[fingerprint])?`输入yes

## 配置Git仓库

切换root

```shell
sudo su root
```

赋予权限

```shell
mkdir /var/repo
chmod -R 755 /var/repo
chown -R git:git /var/repo/
```

创建一个新的库:

```shell
cd /var/repo
git init --bare hexo.git
```

创建` post-receive`文件

```shell
cd hooks
vim /var/repo/hexo.git/hooks/post-receive
```

输入以下内容：

```
#!/bin/bash
git --work-tree=/www/wwwroot/hexo --git-dir=/var/repo/hexo.git checkout -f
```

此处的/www/wwwroot/hexo为网站目录。在右侧目录中的`创建网站`中

# 创建网站

登录面板（宝塔），点击右侧网站，点新建。

![image-20230507123132933](https://img.gtwxxh.cn/i/2023/05/645729a5f0c9c.webp)

申请证书：

![image-20230507123220316](https://img.gtwxxh.cn/i/2023/05/645729d50ef07.webp)

# 本地部署

打开hexo`_config.yml`。找到deploy，填写：

```yaml
deploy:
  type: git
  #repo改为repo: git@域名:/var/repo/hexo.git
  repo: git@SERVER:/var/repo/hexo.git
  branch: master
```

hexo d完成！

# 笨办法

直接将Hexo里public文件夹上传到网站根目录即可！

![image-20230507124422711](https://img.gtwxxh.cn/i/2023/05/64572ca9a9ba8.webp)
