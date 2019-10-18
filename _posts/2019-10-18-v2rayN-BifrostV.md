---
layout: post
categories: posts
title: Scientific Ways To Surf The Internet
subtitle: 关于使用一些免费的线路去科学上网
featured-image: /images/2019-8/Blog14.jpg
tags: [v2rayN,BifrostV,free,tools]
date-string: October 18, 2019
---

今天是那个，没有需求的一天~~然后，快乐肥宅程序员准备玩起之前关注的Golfway，然后，就写下了这篇和Golfway一点关系都没有的代理使用指南，由于不小心看到了一个提供免费节点的网站，还提供让大家直连的方法~然后我就心动啦，给朋友们提供代理再也不用搭在自己的咸鱼服务器上啦~

# 关于网址

首先是提供节点的网址：

>https://free-ss.site/

![blog01](/images/2019-10-18/blog01.png)

不过这个网址直链访问不了，所以这时候需要修改我们电脑的host文件：

![blog06](/images/2019-10-18/blog06.png)

这个时候我就比较推荐电脑上的小工具Listary，双击Ctrl，屏幕上会弹出一个白色输入框，输入host，即刻找到对应文件进行编辑:

![blog07](/images/2019-10-18/blog07.png)

>TIP：这些工具的下载地址我会放在文章结尾

稍微解释下S账号上的几个字符：

![blog05](/images/2019-10-18/blog05.png)

![blog04](/images/2019-10-18/blog04.png)

可以理解为运营商，中国电信，联动，移动的意思
 
修改完host之后，就可以直接访问这个提供免费节点的地址，不过正如该网站分享端所说，这些账号来之不易，所以大家还是珍惜使用。

# 关于PC端工具

由于上述的网站给的是v2ray和酸酸乳的账号，所以我也就把git上两个项目的链接先拉下来：

>v2rayN：https://github.com/2dust/v2rayN

## v2rayN

下载项目的release版本即可，这边只演示v2rayN了：

![blog08](/images/2019-10-18/blog08.png)

![blog09](/images/2019-10-18/blog09.png)

下载解压：

![blog10](/images/2019-10-18/blog10.png)

双击v2rayN.exe，可以看见右下角任务栏多出了一个蓝色小图标：

![blog11](/images/2019-10-18/blog11.png)

回到之前免费上网账号的页面，选择一个V账号的二维码，然后右击蓝色logo，选择扫描屏幕上的二维码：

![blog12](/images/2019-10-18/blog12.png)

![blog13](/images/2019-10-18/blog13.png)

恩，正常的机子，应该都是这个显示~

不过呢，现在还是访问不了外网的，这边可以修改一下参数设置：

![blog14](/images/2019-10-18/blog14.png)

基础设置里的本地端口，不知道的可以选填2019端口，只要不和在使用的端口冲突即可，自定义DNS设置一个8.8.8.8已经够用了。

然后是路由设置，选中域名策略和路由模式，一键生成即可：

![blog16](/images/2019-10-18/blog16.png)

kcp设置是对kcp线路的优化，由于这里使用的是dalao们整理的线路，所以这个kcp设置也不需要设置。

最后是v2rayN设置：

在图片位置，填写：

>https ://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt

其他也是字面意思，看个人爱好配置

![blog17](/images/2019-10-18/blog17.png)

其实上面这串网址也是git上的一个项目，它的项目说明也是蛮有意思的：

![blog18](/images/2019-10-18/blog18.png)

>TIP：gfwlist项目的截图里面所有的汉字都是google机翻，不是针对，本人还是崇尚“富强明主文明和谐”的。

然后只需要启动http代理，选择PAC模式(全局也可以，但是增加不必要的风险)，即可以愉快的科学上网了：

![blog19](/images/2019-10-18/blog19.png)

![blog20](/images/2019-10-18/blog20.png)

这边以utube为例：

![blog15](/images/2019-10-18/blog15.png)


部分账号也已经失效，毕竟是公用的，所以维护起来可能也不太容易。

还有部分公益链接，也传到云盘上了，到时候下载下来全部复制，然后批量导入v2rayN（右键蓝色logo，从剪切板批量导入url）

>TIP：由于账号为免费代理，所以延迟相比自己搭建维护的会稍慢，不过对于日用，访问一些国外论坛学习是够用了，公益链接也是。

# 关于Android端工具

由于本人目前手边没有可供测试的IOS手机，所以就把Android端测试可用的工具进行下简单说明：

>BifrostV
>v2rayNG

由于这两个Apk文件我是从谷歌play上下载，所以我把Apk文件传输到了云盘，以后可以自行更新：

>蓝奏:https://www.lanzous.com/b00t3ioje/
>密码:282m

关于两个软件的使用，就比pc端简单很多


## BifrostV

1）下载安装：

2）点击右上角一个带是“+”的按钮

![blog21](/images/2019-10-18/blog21.png)

![blog22](/images/2019-10-18/blog22.png)

![blog23](/images/2019-10-18/blog23.png)

### v2rayNG

v2rayNg的安装包也放在了云盘里，基础配置和上面的BifrostV类似，就不做过多说明。

# 总结

本篇博客完全是出自搬运公益链接，给大家提供日常学习生活方便而写，所以请大家尊重提供这些链接的dalao们，关于链接还是请珍惜使用。

## END