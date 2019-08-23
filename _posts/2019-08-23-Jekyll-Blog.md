---
layout: post
categories: posts
title: Jekyll
subtitle: 使用Jekyll搭建博客
featured-image: /images/2019-8/Blog03.jpg
tags: [jekyll,blog]
date-string: August 23, 2019
---

#  Jekyll
Jekyll是一个静态的站点生成器，即可以用来制作静态网页，而我的个人博客就是使用jekyll创建的，jekyll可以根据编写的作者编写的源代码，生成一系列静态的html，css，js等文件，jekyll提供了模板，变量以及插件等多样功能，还是相对比较成熟的语言体系，可以拿来编写整个网站。

本篇就主要讲解用jekyll搭建自己的博客，个人觉得，互联网时代下，一份部署在网络上的个人简介是很重要的，这是一种比较直观的提现自己个人价值的一份说明，而且当你把这个链接展示给你的面试官的时候，足够显示自己的对待专业的认真和价值。所以，这篇文章将对使用jekyll搭建博客进行说明。

相对于市面上主流的博客搭建方式，Wordpress、Typech等，jekyll生成的站点是一个静态站点，也就是没有数据库支撑，这门语言是由ruby编写的，然而我们制作网站只需要通过编写MarkDown文档，使用liquid模板就可以生成。这也是我之前讲解了MarkDown语法的原因之一。

静态网站自然有静态网站的好处，不需要数据库支撑，自然不用去设置评论等功能，但是如果一定要去做这一块的工作，可以通过嵌入Disqus，gitment等插件来实现功能；其次呢，静态网站，说到底也就是只是一堆html，css等代码，比起动态网站，我们没有必要多么熟练的掌握一些类似，java语言，php语言等，掌握好5min学会的MarkDown语言已经够我们日常的发布文章了，另外，静态网站更为安全，不容易受到攻击。然后我之前讲解github的原因就是，在github上创建库后，我们可以使用github的免费域名，我们可以直接把我们的项目部署到github上，这样，我们就能够拥有简约，低成本而有格调的个人博客。

本篇文章不介绍ruby以及ruby的版本管理系统，也不介绍使用jekyll的环境配置，以及从头并自我设计，只是快速的介绍如果使用jekyll已经存在的主题，然后制作自己blog。对以上所述的感兴趣的，可以通过下面的网站访问:

>ruby: https://www.ruby-lang.org/zh_cn/

>jekyll: https://jekyllrb.com/

# Jekyll Theme

首先，我们需要访问这个jekyll模板网站：

>http://jekyllthemes.org/

![Bolg01](/images/2019-08-23/Blog01.png)

然后呢，选中自己喜欢的页面，比如：

![Blog02](/images/2019-08-23/Blog02.png)

Download自然就是下载模板了，模板会以.zip文件格式下载到本地。

Demo是演示，我们可以点击此处预览该模板的大概。

License是该模板的说明。

而Homepage选项是直接跳转到此模板在github上的仓库，我们之后可以使用git bash工具将项目拉到本地上。

![Blog03](/images/2019-08-23/Blog03.png)

我们可以复制该路径，然后在打开本地的git bash框，输入：

    git clone https://github.com/ShawnTeoh/matjek.git

![Blog04](/images/2019-08-23/Blog04.png)

然后打开本地的仓库就可以看见这些东西：

![Blog05](/images/2019-08-23/Blog05.png)

这时候，我们可以

    ll -a
    rm -rf .git
    git init

查看该库中的所有文件，把.git文件删除，然后再把这个库初始化，把这个库转换成我们自己的git项目，然后如果我们电脑安装了visual studio Code ，我们就可以直接在bash界面中输入

    code .

![Blog06](/images/2019-08-23/Blog06.png)

进入vsc界面对文件进行编辑

![Blog07](/images/2019-08-23/Blog07.png)

接下来就是分析一下改模板的目录结构了。

首先就是_config.yml文件，这个是模板的配置文件：

![Blog08](/images/2019-08-23/Blog08.png)

首先,title就是标题，description就是对该网页描述，url就是内嵌的访问地址，不过如果我们部署到github上之后，建议把该url后的地址删除，Repository就是该模板的库了，paginate表示一个页面最多显示的5篇文章.

#MatJek specific configurations这一块如果没有需要，就可以删掉

#Build settings一块就指名了文章是按照MarkDown语言编写的，需要handler安装的gem依赖等。

然后看下目录，

目录名|内容
:-:|:-:
_inclueds|公共的模板代码片段，组成网页头，网页底，模块按键等内容
_layout|存放模板文件的排版格式
_post|以MarkDown格式编写，存放博客内容
assert|存放css，js等文件

详细的Jekyll 中配置和模板语法可以参考下面的链接（是某位dalao写的）：

>https://git.io/fA9KQ

然后我们就来看下模板的文章格式：

![Blog09](/images/2019-08-23/Blog09.png)

每次需要新增博客的时候，我们需要修改的头部信息有title，date，tag等变量信息，然后呢正文就是MarkDown语法，不再介绍了。

等我们的文章都写完了，就可以把全部文件都上传：

    git add -A .
    git commmit -m "blog"
    git push

上传到我们的库中。然后我们就可以通过我们的域名访问我们的博客了。

备注：如果第一次我们访问我们自己的博客，发现博客的格式不对，像css格式未正常加载，或者直接显示404 Not Found，我们可以在当前页面打开检查页面，或者点击F12，查看未正常加载的资源，查看Request URL是否与我们配置的有出入，如果有，修改配置文件里的url为github库中资源文件的路径即可解决。

如果需要深入了解Jekyll语言，我们就需要去掌握ruby，gem以及liquid等方面的知识，本博客不做详解
