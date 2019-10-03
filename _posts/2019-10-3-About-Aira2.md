---
layout: post
categories: posts
title: About Aira2 & PanDownload
subtitle: 关于在windows上aira2的安装及使用
featured-image: /images/2019-8/Blog12.jpg
tags: [aira2,PanDownload,]
date-string: October 3, 2019
---
主要解释如何在win操作系统下，部署aira2客户端，并且配合油猴插件，Pandownload脚本，实现全速下载百度云盘资源。

# 一些准备

首先，得给浏览器安一个油猴(官网/chrome)。
>http://www.tampermonkey.net/
>https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo

如果没有代理，chrome的网上应用店访问不了（即第二条链接）。

![blog01](/images/2019-10-03/blog01.png)

![blog02](/images/2019-10-03/blog02.png)


第二步就是在安装油猴脚本，可以访问以下网址：

>https://greasyfork.org/zh-CN/scripts/383059-pandownload网页版-百度网盘不限速直链下载-jaeger

![blog03](/images/2019-10-03/blog03.png)

TIP:Greasy Fork是一个查找脚本很方便的网站，这里列出网址，方便学习使用

>https://greasyfork.org/zh-CN

安装完成之后，脚本列表里会添加这个PanDownload。

![blog04](/images/2019-10-03/blog04.png)

![blog05](/images/2019-10-03/blog05.png)


将脚本选择已启用，之后在查看别人的分享链接的时候，都会进行一次重定向，跳转到pandownload的页面。

比如，现在我得到一个如：https://pan.baidu.com/dy/test 的链接，那我访问这个链接的时候，脚本会自动在链接的baidu之后添加wp ，即跳转到 https://pan.baiduwp.com/dy/test 这个页面：

![blog06](/images/2019-10-03/blog06.png)

同时，浏览器会跳转到pandownload的页面（验证码输入错只会刷新页面，不会报错，亲测）：

![blog07](/images/2019-10-03/blog07.png)

![blog08](/images/2019-10-03/blog08.png)

选中下载内容后跳转页面，会给出一个直链和一个Aira2的链接，然后就是关于Aira2配置的内容：

![blog09](/images/2019-10-03/blog09.png)

# Aira2配置

### 运行Aira2
以官方最新版本为例：
>https://github.com/aria2/aria2/releases

![blog10](/images/2019-10-03/blog10.png)

下拉到Asserts界面,点击即下载:

![blog11](/images/2019-10-03/blog11.png)

下载到本地后，解压：

![blog12](/images/2019-10-03/blog12.png)

然后点击以下地址，将这个包解压到上面的文件中去

>https://www.moerats.com/usr/down/Aria2_Win.7z

![blog13](/images/2019-10-03/blog13.png)

首先点击start.bat，弹出一个cmd窗口，这个窗口需要一直保持，否则下载进行不了或者中断。

![blog14](/images/2019-10-03/blog14.png)

### 使用Web下载

本人使用的是AiraNg，即本地的web端,在以下链接地址下载解压：

>https://github.com/mayswind/AriaNg/releases

![blog16](/images/2019-10-03/blog16.png)

![blog15](/images/2019-10-03/blog15.png)

然后浏览器就会跳出Aira2的页面：

![blog17](/images/2019-10-03/blog17.png)

配置完成后，回到之前的PanDownload界面：

![blog18](/images/2019-10-03/blog18.png)

由于是本机启动的Aira2，所以主机和端口配置就如图配置，下载路径自己配置就好。

![blog19](/images/2019-10-03/blog19.png)

确认后，显示已添加到下载列表：

![blog22](/images/2019-10-03/blog22.png)

由于下的比较快，所以回到下载页面也就快下完了。

![blog20](/images/2019-10-03/blog20.png)

之前的cmd窗口会显示你的下载内容：

![blog23](/images/2019-10-03/blog23.png)

文档显示：

![blog21](/images/2019-10-03/blog21.png)

