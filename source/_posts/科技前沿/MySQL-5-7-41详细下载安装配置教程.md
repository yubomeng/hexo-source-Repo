---
title: MySQL 5.7.41详细下载安装配置教程
tags: MySQL
categories: 科技前沿
cover: 'https://s3.qjqq.cn/37/65649f673d67b.webp!color'
top_img: 'https://s3.qjqq.cn/37/65649f673d67b.webp!color'
ai:
  - >-
    这篇教程详细地介绍了在Windows系统上安装和配置MySQL
    5.7.41的步骤。主要包括下载MySQL安装文件、配置环境变量、编辑my.ini配置文件、安装MySQL服务、设置MySQL密码等内容。同时还提供了一些解决常见问题的链接，方便读者在遇到问题时进行参考。总体来说，这篇教程对于刚接触数据库的小白用户来说非常友好，提供了清晰的步骤和截图，帮助他们顺利完成MySQL
    5.7.41的安装和配置过程。文章中还解释了一些常见错误的解决方法，让读者可以更好地理解和应对可能遇到的问题。
  - >-
    需要注意的是，文章中的部分操作需要以管理员身份运行命令提示符，这一点对于初学者来说很重要。同时，备份重要数据和谨慎操作也是非常关键的，以免造成数据丢失。整体来看，这篇教程非常实用，对于想要在Windows系统上安装MySQL
    5.7.41的用户来说是一份很好的指南。
abbrlink: a4c43b96
date: 2023-11-27 21:43:17
---

# MySQL 5.7.41详细下载安装配置教程

MySQL 5.7.41 详细下载安装配置教程

前言

`若你想安装MySQL 5.7版本，但已经存在MySQL 8.0版本的服务，你可以尝试以下步骤来解决问题：`

1.  打开命令提示符（以管理员身份运行）。
2.  导航到MySQL 8.0安装目录，即"D:\MYSQL\mysql-8.0.31-winx64\bin"。
3.  运行以下命令卸载MySQL 8.0服务：

```sh
mysqld --remove
```

4.  确认MySQL 8.0服务成功卸载后，导航到MySQL 5.7安装目录，即"D:\MYSQL\mysql-5.7.41-winx64\bin"。

5.  运行以下命令安装MySQL 5.7服务：

   ```sh
   mysqld --install
   ```

6. 安装完成后，你可以启动MySQL 5.7服务并进行相应配置。

`请谨慎操作，并确保在卸载MySQL 8.0之前备份重要数据，以免造成数据丢失。`（mysql 5.7安装mysql 8.0反之亦可）



## 在安装MySQL的时候会遇到很多问题，博客上有很多解决问题的办法，在这里我附上一些链接，遇到问题的朋友们可以阅读参考哈~本文主要针对于刚接触数据库的小白，来安装MySQL数据库。目前官网上的MySQL版本有5.5，5.6，5.7和8，在开发的时候我们一般要选择比最新版低1到2个版本的，因此我选择了5.7作为要安装的数据库。

#### 一、下载步骤

1.  访问官方网站：https://www.mysql.com/
    选择Downloads下的Community

![](https://s3.qjqq.cn/37/65649305d44f1.webp!color)

下拉，找到[MySQL Community (GPL) Downloads »](https://dev.mysql.com/downloads/)

![](https://s3.qjqq.cn/37/6564934ac001d.webp!color)

![](https://s3.qjqq.cn/37/65649387d356f.webp!color)

2. 下载对应的版本
   点击上图的**MySQL Community Server**,进入下载界面：

   ![](https://s3.qjqq.cn/37/656493e52aacb.webp!color)

​			根据你电脑的版本选择**下载对应的ZIP文件**，我的电脑是64位的，因此选择这项进行下载，点击**Download**会进入以下界面：

![](https://s3.qjqq.cn/37/6564944017e3f.webp!color)

点击**No thanks，just start my download**就好，然后开始下载

![](https://s3.qjqq.cn/37/6564946a5649e.webp!color)

下载完毕后将文件解压到你想保存到的盘和目录内。我是将文件解压到`D:\MYSQL\`目录下面。

![](https://s3.qjqq.cn/37/656494af8663e.webp!color)

以上就完成了下载的全部工作。(上述的`data`目录和`my.ini`是我后续新建的)

#### 二、配置环境变量

1. 系统—>高级系统设置—>环境变量—>系统变量

![](https://s3.qjqq.cn/37/65649534ca651.webp!color)

![](https://s3.qjqq.cn/37/6564955fdd8a7.webp!color)

名为：**MYSQL_HOME**，添加你的mysql-5.7.41-winx64文件夹所在位置。
我的是在**D:\MYSQL\mysql-5.7.41-winx64**，如图：

![](https://s3.qjqq.cn/37/656495b8bea6e.webp!color)

2. 编辑Path，添加`%MYSQL_HOME%\bin`到原有值的后面，如图：

![](https://s3.qjqq.cn/37/6564962537f65.webp!color)

#### 三、配置my.ini文件

在你的mysql-5.7.41-winx64目录下新建my.ini文件，我的是在`D:\MYSQL\mysql-5.7.41-winx64`目录下新建，my.ini文件的内容为：

```ini
[mysqld]
#端口号
port = 3306
#mysql-5.7.41-winx64的路径
basedir=D:\MYSQL\mysql-5.7.41-winx64
#mysql-5.7.41-winx64的路径+\data
datadir=D:\MYSQL\mysql-5.7.41-winx64\data 
#最大连接数
max_connections=200
#编码
character-set-server=utf8

default-storage-engine=INNODB

sql_mode=NO_ENGINE_SUBSTITUTION,STRICT_TRANS_TABLES

[mysql]
#编码
default-character-set=utf8 

```

创建完成后进入下一步。

#### 四、安装MySQL

1. 在输入框内输入cmd，**以管理员的身份运行**，注意这里**一定一定一定要以管理员的身份运行**，否则在安装过程中会出现因为管理权限不够而导致的**Install/Remove of the Service Denied!（安装/卸载服务被拒绝）**，这一点非常重要！

![](https://s3.qjqq.cn/37/656496c91bdb3.webp!color)

2. 在**cmd**中进入到**D:\MYSQL\mysql-5.7.41-winx64\bin**目录下:

![](https://s3.qjqq.cn/37/65649758a5a79.webp!color)

输入安装命令：`mysqld -install`，若出现**Service successfully installed**，证明安装成功；如出现**Install of the Service Denied**，则说明没有以管理员权限来运行cmd：

![](https://s3.qjqq.cn/37/656497b3af844.webp!color)

然后继续输入命令：`mysqld --initialize`，此时不会有任何提示：

![](https://s3.qjqq.cn/37/656497f9bc161.webp!color)

再输入启动命令：`net start mysql`，出现以下提示证明MySQL启动成功：

![](https://s3.qjqq.cn/37/65649826baea4.webp!color)

#### 五、设置MySQL密码

1. 在这里设置密码主要是为了解决：ERROR 1045 (28000): Access denied for user ‘root’@‘localhost’ (using password: NO)的问题
2.  首先停止MySQL服务,输入命令行`net stop mysql`：

![](https://s3.qjqq.cn/37/6564988428f12.webp!color)

3. 在D:\MYSQL\mysql-5.7.41-winx64目录下找到**my.ini**，在[mysqld]字段下任意一行添加`skip-grant-tables`，保存即可：

![](https://s3.qjqq.cn/37/656498be09101.webp!color)

4. 重启MySQL,输入启动命令：`net start mysql`，出现以下提示证明MySQL启动成功：

![](https://s3.qjqq.cn/37/656498e66f2fe.webp!color)

在输入命令`mysql -u root -p`，不需要输入密码，直接回车：

![](https://s3.qjqq.cn/37/65649908408ed.webp!color)

进入MySQL成功！

5. 输入命令行`use mysql`，进入数据库：

   ![](https://s3.qjqq.cn/37/656499309a247.webp!color)

6. 输入命令行`update user set authentication_string=password("xxxxxx") where user="root";`xxxxxx是你设置的新密码，敲击回车后若出现以下信息，证明修改成功！

![](https://s3.qjqq.cn/37/6564996d66997.webp!color)

7. 手动停止MySQL服务，在win10搜索栏内输入**服务**，找到**MySQL**。点击右键，然后点击停止即可。

![](https://s3.qjqq.cn/37/656499ab8f653.webp!color)

然后在刚刚的my.ini文件中删除**skip-grant-tables**这一行，保存关闭。

8.  再次启动cmd（管理员身份），输入启动命令：`net start mysql`，再输入`mysql -u root -p`，再输入你刚刚设置的密码，出现以下信息证明设置成功！

   ![](https://s3.qjqq.cn/37/65649a06ca1d9.webp!color)

然后输入命令行`use mysql`验证一下，结果报错：

![](https://s3.qjqq.cn/37/65649a211d26f.webp!color)

既然没有重置密码，那就重置一下呗
键入命令行`alter user user() identified by "xxxxxx";`我的密码是123456，因此我键入 `alter user user() identified by "123456";`回车！离胜利越来越近了！
再次输入命令行`use mysql`验证一下，成功！

![](https://s3.qjqq.cn/37/65649a7fb004b.webp!color)

#### 问题：

1. [找不到my.ini文件](https://blog.csdn.net/baidu_41909653/article/details/82148455)
2. [ERROR 1045 (28000): Access denied for user ‘ODBC’@‘localhost’ (using password: NO)](https://blog.csdn.net/weixin_41688619/article/details/79879003)
3. [ERROR 1045 (28000): Access denied for user ‘ODBC’@‘localhost’ (using password: YES)](https://blog.csdn.net/weixin_41688619/article/details/79879003)
4. [Unknown column ‘password’ in ‘field list’](https://blog.csdn.net/u010603691/article/details/50379282)
5. [You must reset your password using ALTER USER statement before executing this statement](https://blog.csdn.net/hj7jay/article/details/65626766)