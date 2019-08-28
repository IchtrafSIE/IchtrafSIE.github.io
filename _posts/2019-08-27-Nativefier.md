---
layout: post
categories: posts
title: Nativefier
subtitle: 一个为任何网页生成应用程序的工具
featured-image: /images/2019-8/Blog06.jpg
tags: [ nativefier,github,Icofx]
date-string: August 27, 2019
---
今天在访问油管的时候看到这么一个好玩的工具，可以把任意的网站都封装成应用程序，由于我使用的是windows客户端，所以我去学习了如何在windows端使用该工具。该工具的仓库地址如下：

    https://github.com/jiahaog/nativefier

# 一、Nativefier

Nativefier是一个命令行工具，可以轻松地为任何具有简洁和最小配置的网站创建桌面应用程序。应用程序被包裹电子在操作系统中可执行文件（.app，.exe，等），在Windows，MacOS和Linux的使用。

以上是比较官方的概述，而我使用该工具其实还是由于好奇和好玩，比较适合现在的我，等于把自己想要访问的网站的所有内容下载到本地，然后在本地打开，就不需要通过ip地址或者域名访问。个人暂时还不会去优化服务器配置，增加安全性，如果在我去投简历之前还没有学会的话，这个工具可以展示我的博客和项目也是不错的。

### 安装前提

    系统要求：macOS 10.9+ / Windows / Linux
    插件需求：Node.js >=6（地址：https://nodejs.org/en/）

![blog01](/images/2019-08-27/blog01.png)

由于个人使用是win环境，所以本篇文章只针对win环境下nativefier的使用。node.js脚本下载完成之后，双击安装即可，会自动配置环境变量。等到安装完成，我们只需要打开win自带的终端，win+r,输入cmd并且输入npm，得到如下结果，说明我们已经安装成功了。

![blog03](/images/2019-08-27/blog03.png)

然后就是安装nativefier，继续在cmd中输入：

    npm install nativefier -g

等待其安装就可以，安装完成后会得到大概如下的提示信息：

![blog02](/images/2019-08-27/blog02.png)

### 操作

接下来我们就可以通过nativefier命令来下载一些网站了。

比如说，我的个人博客的网址是https://ichtrafsie.github.io，
那么我就可以在cmd中输入：

    nativefier "https://ichtrafsie.github.io"]

对该网站进行下载到本地并且封装成为一个应用程序，当然，也可以在下载之前对其进行命名。

    nativefier --name "Dyblog" "https://ichtrafsie.github.io/"

![blog10](/images/2019-08-27/blog10.png)

图示的图标修改下面会讲到，先看下效果图：

![blog11](/images/2019-08-27/blog11.png)

# 二、Icofx
既然下载了自己想要下载的网站，我们也可以对其应用程序的图标进行一些自定义，所以我推荐一个名为Icofx的软件，下载地址如下:

    (官网)https://icofx.ro
    (蓝奏)https://www.lanzous.com/b405554/

![blog06](/images/2019-08-27/blog06.png)

这个在图标DIY上是一个很强大的工具，往往是拿来用作设计，不过我们如果只是想通过这个工具将一些图片作为软件应用图标，只需要下载蓝奏网盘的使用就可以，官方的只有30天的使用期限。但是如果想要使用该软件进行商业用途，需要购买该软件获得该软件的营业许可和执照等。

### 简单操作说明

打开icofx软件，点击文件-打开-选择图片，然后就会出现下图演示(先前使用过)：

![blog07](/images/2019-08-27/blog07.png)

由于是将jpg文件转换为ico图标，所以选择第二个。

![blog08](/images/2019-08-27/blog08.png)

然后另存为就可以使用了，比如我定义的名字为Dy.ico

![blog09](/images/2019-08-27/blog09.png)

然后我们回到cmd窗口，输入

    nativefier --icon Dy.ico "https://ichtrafsie.github.io/"

这样我们下载的网页就可以使用自定义的图标了。

由于是一个相对有趣的工具，所以我也只是学会了使用而非研究，如果对这个工具感兴趣，可以参考下面的API文档：

>https://github.com/jiahaog/nativefier/blob/master/docs/api.md

## END