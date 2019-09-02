---
layout: post
categories: posts
title: Git in Idea & Visual Studio Code
subtitle: 在idea和vsc上连接git远程仓库
featured-image: /images/2019-8/Blog09.jpg
tags: [Idea,Visual Studio Code,Git]
date-string: September 02, 2019
---
最近琢磨着准备上传个自制的项目到git或者自己的服务器上，到时候面试的时候能把握住自己的点，然后花了点时间搞了下。

# Git in Idea

Idea是个人日常学习java常用的工具，感觉比eclipse或者myeclipse方便很多：

![blog12](/images/2019-09-02/blog12.png)

当我们想绑定idea和Git远程仓库的时候，需要进行如下操作：

首先选择菜单栏的VCS-Import into Version Control-share Project on Github。

![blog01](/images/2019-09-02/blog01.png)

然后会提示你输入自己的git账号和密码，进行绑定后，会读取你的项目名称，并且询问你是否将此项目分享到git远程仓库中。选中share后，会出现提交列表，显示出该项目中的条列，由于本项目单纯用于测试，所以全部提交就可以，点击Add后，idea右下角就会有提示信息。

![blog02](/images/2019-09-02/blog02.png)

![blog03](/images/2019-09-02/blog03.png)

![blog04](/images/2019-09-02/blog04.png)

当显示成功分享后，可以打开浏览器，查看自己的库中多出了一个以刚刚项目名命名的存储库：

![blog05](/images/2019-09-02/blog05.png)

![blog06](/images/2019-09-02/blog06.png)

不过该项目只是按照自己编写的格式里来创建的，并没有该项目的说明文档以及相关文件，首先点击Add a README，由于是个测试项目，所以不添加过多说明。

不过虽然添加到了远程仓库，但是不能直接访问到，所以可以按照创建Repository的方式，在setting-Git Page上选择分支，如果git给的域名用的不舒服，可以自行添加个人域名。

![blog07](/images/2019-09-02/blog07.png)

git说到底只是一个功能强大的版本控制器，所以在idea操作对本地项目修改后上传等一系列操作，只需要点击idea底部工具栏的version Control，进而有一些与项目修改长传查看的按钮，例如refresh：刷新；commit：更新；revert：回退；show Different：展示修改的点等等。

![blog08](/images/2019-09-02/blog08.png)

![blog09](/images/2019-09-02/blog09.png)

以上传为例：

![blog10](/images/2019-09-02/blog10.png)

点击绿色的钩会出现以上界面，相比git bash更具有优势的是图形化界面可以更直观的查看修改前后的不同，确认修改后再Commit Message框中添加修改信息，类似于git bash中

    git commit -m "修改信息"

选择commit & push就可以提交改动到远程仓库。

# Git in Visual Studio Code
vsc是比较喜欢的MarkDown编辑器，除了编辑MarkDown文本之外，其兼容各种插件的能力也是十分优秀，内置git支持，详细使用可以查看官方文档：

>https://code.visualstudio.com/docs/editor/versioncontrol

![blog14](/images/2019-09-02/blog14.png)

![blog13](/images/2019-09-02/blog13.png)

在win环境中安装了git后，vscode中也可以直接调用pwoershell终端，并且使用git命令。

![blog15](/images/2019-09-02/blog15.png)

如果我们远程创建了一个Test的存储库，想在本地初始化该仓库的时候，可以直接在本地的终端运行创建命令，创建演示如下：

![blog16](/images/2019-09-02/blog16.png)

然后就可以直接对readme.md进行编译。

![blog17](/images/2019-09-02/blog17.png)

保存后再如往常在git bash一样进行提交:

![blog18](/images/2019-09-02/blog18.png)

刷新浏览器上的仓库页面，可以看到之前的提交：

![blog19](/images/2019-09-02/blog19.png)

# 小结

虽然可能这两款编辑器与git连接的很多功能我暂时还未学会，不过基础的提交和更新都可以像git bash那样在vsc中运行那样完成，来日方长，可以慢慢来。


END
