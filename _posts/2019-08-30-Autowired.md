---
layout: post
categories: posts
title: Autowired
subtitle: 自动注解的原理以及SSM配置遇到的问题
featured-image: /images/2019-8/Blog08.jpg
tags: [java,SSM,proxy]
date-string: August 30, 2019
---

昨天配置了SSM的基本配置，然后今天在配置事务的时候，遇到了一些问题：

![blog01](/images/2019-08-30/blog01.png)

配置log4j.properties，查看更多启动的时候的错误信息：

![blog02](/images/2019-08-30/blog02.png)

再次运行：

![blog03](/images/2019-08-30/blog03.png)

无法创建bean，Injection of autowired dependencies failed表示自动代理失败，刚开始的时候以为是jar包有问题，mysql -connect -java的jar包版本太低，和环境不兼容，不过更新jar包后还是报错。查阅资料后，可能存在事务未提交的问题，所以在进行注解配置的时候将Controller类和其他类分别按先后加载，让springmvc的配置文件中，让@Transactional生效，进而注册事务。

做法就是另写一个applicationContext.xml，在其中配置如下

![blog05](/images/2019-08-30/blog05.png)

然后修改先前的applicationContext.xml文件为applicationContext1.xml，并且修改其中对扫描注解的配置。

![blog06](/images/2019-08-30/blog06.png)

最后修改web.xml文件，调整加载顺序，并且启动tomcat。

![blog07](/images/2019-08-30/blog07.png)

结果还是报了个错:

![blog04](/images/2019-08-30/blog04.png)

是无法自动配置itemsController的方法，@proxy表示自动加载，查阅资料后，发现@Proxy为接口代理，不是类代理，回头看我的Controller层，果然自动装载的是类代理，所以一直自动创建失败。

![blog08](/images/2019-08-30/blog08.png)

修改ItemsService为其接口类IItemsSerice，后再次启动tomcat，事务配置成功：

![blog09](/images/2019-08-30/blog09.png)

![blog10](/images/2019-08-30/blog10.png)

框架是很底层的知识点，多研究研究总是好的。

END