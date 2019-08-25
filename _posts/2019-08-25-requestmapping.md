---
layout: post
categories: posts
title: RequestMapping
subtitle: SpringMVC中的@RequestMapping注解
featured-image: /images/2019-8/Blog04.jpg
tags: [SpringMVC,@RequestMapping,github]
date-string: August 25, 2019
---

# 一、Git GUI的一个问题
今天打开Git GUI，准备对我的储存库进行操作的时候，弹出了一个对话框：

![blog01](/images/2019-08-25/blog01.png)

大概意思是该储存库目前有256个松散项目，选择了是，弹出了success的提示框：

![blog02](/images/2019-08-25/blog02.png)

但从网络上查找的资料看，有些人计算按照步骤走，自己的库中资源也并未得到优化，所以，当遇到这种提示框的时候，最好打开bash命令框，然后cd到本地的储存库的路径上，然后输入

    git gc --aggressive 

得到如下结果：

![blog03](/images/2019-08-25/blog03.png)

我们的松散资源就得到了优化了。

在我们日常使用我们的库，在里面压缩或者删除资源时，可能会删除先前调用git add创建的对象，以及其他的一些情况，造成资源松散，这时候我们可以使用上面的命令，解决该问题，来提高磁盘空间的体用率。同时建议用户定期在每个储存库中运行此操作，提高磁盘的性能。

# 二、关于SpringMVC的@Requestmapping注释

今天在学习SpringMVC的注解开发时，在controll层使用@RequestMapping注解配置的时候，页面一直404，找不到资源,而console也没有错误信息提示。404页面一直显示。

    The origin server did not find a current representation for the target resource or is not willing to disclose that one exists.


![blog04](/images/2019-08-25/blog04.png)

![blog05](/images/2019-08-25/blog05.png)

我开始的时候一直不理解为什么/WEB-INF/之前有个user，单纯的看这个类的话，访问的时候输入http://localhost:8080/user/list.do，就能访问到目录下的userlist.jsp文件，所以我打开检查资源，查看资源路径是不是错了：

![blog06](/images/2019-08-25/blog06.png)

但是这和我输入的网址一样，我get不到任何信息。

然后我尝试去掉方法外面的@RequestMapping类，重新部署服务器，只访问http://localhost:8080/list.do,结果访问成功，但是这毕竟不是办法，我想在一个注解配置下实现多种方法，把相关的方法整合在同一个类中，提高代码可读性。

然后呢，我去查找资料，发现有这么一个说法，

![blog07](/images/2019-08-25/blog07.png)

虽然WEB-INF下的.jsp文件用户的确不能直接访问到，但是如果资源路径指定正确的话到的话还是可以访问的到。不过却提现我是不是WEB-INF的资源路径书写错误。因为之前用在配置文件里用bean标签一步步配置url处理映射，适配器等步骤，都是了解，所以也没调试过代码，所以当我回看DispatcherServlet-servlet.xml的时候，发现配置资源视图解析器的/WEB-INF/路径的时候，前面一个斜杠丢掉了，所以404页面才会把我的第一个注释放在WEB-INF/之前，路径的确是有问题的。

![blog08](/images/2019-08-25/blog08.png)

![blog09](/images/2019-08-25/blog09.png)

所以当我在配置上添加斜杠后，访问就正常了，可以进行后面的功能编写。

![blog10](/images/2019-08-25/blog10.png)