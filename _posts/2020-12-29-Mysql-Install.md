---
layout: post
categories: posts
title: Mysql-Install
subtitle: MySQL5.7安装说明
featured-image: /images/2019-8/Blog15.jpg
tags: [MySQL5.7,Install]
date-string: December 29, 2020
---

重装了电脑，忘记如何使用客户端安装MySQL，记录解压安装过程

# 下载地址

>MySQL下载地址：https://mirrors.tuna.tsinghua.edu.cn/mysql/downloads/MySQL-5.7/

![blog01](/images/2020-12-29/1.png)

这里选择的是国内清华源，由于源较多，ctrl+f搜索win，下载64位MySQL压缩包。

# 解压配置

下载后，解压至任意目录，此时解压的版本还需要添加两个文件。

![blog01](/images/2020-12-29/2.jpg)

1、新建记事本文件，复制粘贴以下内容（安装目录以实际目录为准）

```
[mysql]
# 设置mysql客户端默认字符集
default-character-set=utf8
[mysqld]
#设置3306端口
port = 3306
# 设置mysql的安装目录（填自己的安装地址就行）
basedir=E:\mysql-5.7.30-winx64
# 设置mysql数据库的数据的存放目录
datadir=E:\mysql-5.7.30-winx64\data
# 允许最大连接数
max_connections=200
# 服务端使用的字符集默认为8比特编码的latin1字符集
character-set-server=utf8
# 创建新表时将使用的默认存储引擎
default-storage-engine=INNODB
```

2、创建一个名为 data 的文件夹

接下来，打开环境变量配置，新建如下

```
1、
变量名：MYSQL
变量值：E:\mysql-5.7.30-winx64

2、
变量名：PATH
变量值: E:\mysql-5.7.30-winx64\bin
```

保存后，右键菜单win图表，选择以管理员身份打开powershell
![blog01](/images/2020-12-29/3.jpg)
1、初始化数据库：

```
mysqld --initialize 
```
data文件夹目录下， 会生成一些文件，其中有一个命名方式为主机号的.err文件 其中保存有初始化生成的密码


2、注册MySQL 服务
```
mysqld -install MySQL
```

3、启动MySQL 服务

```
net start mysql
```

4、进入数据库
```
mysql -uroot -p
```

5、提示 Enter password： 输入自动生成的密码，登录成功，可以使用第三方工具创建连接

6、如果输入密码，提示密码验证失败，则需要以下操作

* 打开创建的my.ini，于[mysqld]下插入一行：

    **skip-grant-tables**
* 重启mysql服务
    ```
    net stop mysql

    net start mysql
    ```
    *此时，再次输入 mysql -uroot -p 进入数据库：

    提示 Enter password：

    再次回车，进入服务（其实直接输入 mysql也可以进）

* 进入服务后，输入
```
flush privileges;
```

>此命令可以将后续需要修改数据库用户数据和权限修改后，直接生效。

* 此时，执行
```
set password root@localhost=password('root');
```
更新密码成功！

* 输入exit 退出界面，将my.ini配置文件中的```skip-grant-tables```删除，重启服务即可。

