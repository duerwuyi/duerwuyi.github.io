---
title: 博客搭建过程
date: 2022-01-27 16:41:41
author: Duerwuyi
tags: [blog, hexo, icarus, Web]
categories: [Web, blog]
---

# 一、写在前面

写这篇文章时,整体网站搭建如下：

![init-page](init.png)

此时，项目已部署到Github pages。

github仓库地址：

https://github.com/duerwuyi/duerwuyi.github.io

框架：使用hexo博客框架，icarus主题。该主题的完成度非常高，三栏的布局模式使主页面有着爆炸的信息量，简约的设计风格又不让人感觉冗余。

然而此时博客内的文章只字未写，且对于博客系统的改造还未开动。因此写下此篇博文，边撰写边对该项目进行魔改。

第二部分将简略记录框架搭建+服务器部署+基本配置方面的内容，第三部分将同步解决后续的各类问题。

ps：

Hexo官网：https://hexo.io/zh-cn/

icraus官方文档及预览：https://ppoffice.github.io/hexo-theme-icarus

icarus的github仓库地址：https://github.com/ppoffice

---

# 二、前置准备

略，有空填坑。（防止忘记：这一部分主要是关于Hexo的npm安装和命令，Git配置，部署到github pages，以及config.yml的修改）

先贴出hexo的readme：

### Create a new post

``` bash
$ hexo new "My New Post"
```

More info: [Writing](https://hexo.io/docs/writing.html)

### Run server

``` bash
$ hexo server
```

More info: [Server](https://hexo.io/docs/server.html)

### Generate static files

``` bash
$ hexo generate
```

More info: [Generating](https://hexo.io/docs/generating.html)

### Deploy to remote sites

``` bash
$ hexo deploy
```

More info: [Deployment](https://hexo.io/docs/one-command-deployment.html)

---

# 三、静态界面修改

## 静态图像

在 icraus/source/img下修改图片，里面有着静态图片资源如logo（网站左上角），头像等。

在_config.icarus.yml中可以修改路径：

```
    logo: /img/logo.svg
```
修改图标也是一样，使用下方的路径，将图标变为流汗黄豆。
```
favicon: /img/favicon.ico
```
