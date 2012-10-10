---
layout: post
title: "Buildroot 用户手册"
date: 2012-09-30 11:08
comments: true
categories: 
---
官方网址:<http://buildroot.uclibc.org/downloads/manual/manual.htm>

粗略翻译,自己用.
#第一章. 关于Buildroot
#第二章. 获得Buildroot
Buildroot大概每三个月发布.也支持直接git访问和每日快照.

发布版地址:<http://buildroot.net/downloads/>.

最新的快照版本 < http://buildroot.net/downloads/snapshots/buildroot-snapshot.tar.bz2> .预览快照在 <ttp://buildroot.net/downloads/snapshots/>

通过git下载:"访问git"页面(<http://buildroot.net/git.html>)或者Buildroot网站(<http://buildroot.net>).快速方法:

`$ git clone git://git.buildroot.net/buildroot`

#第三章. 使用Buildroot
##3.1 配置和一般用法
注意,您可以(并且应该)以普通用户构建,没有必要使用root用户配置和使用Buildroot.第一步.配置:

`$ make menuconfig`

或者图形化的配置:

`$ make xconfig`

或者

`$ make gconfig`

来运行基于Qt或者GTK的配置工具.

所有make命令都哦需要配置工具.所以也许需要安装"开发"包来完成.在类Debian系统(Debian,Ubuntu,等等)中：`menuconfig`需要`libncurses5-dev`包，`xconfig`界面需要`libqt4-dev`包,而`gconfig`需要`libglib2.0-dev`，`libgtk2.0-dev`和`libglade2-dev`包。

让我开始吧:

`$ make`

你**永远不该**使用`make -jN`

这个命令完成以下几步:
* 下载源文件
* 配置
* 构建/安装
* 构建内核镜像(如果选择)
* 构建bootloader镜像
* 按照选择的格式创建根文件系统

输出保存在单一的目录`output/` .这个目录包括一系列子目录:
* `images/`
* `build/`
* `staging/`
* `target/`
* `host/`
* `toolchain`

##3.2 离线构建

如果进行离线构建,你只需要下载所有的源代码.执行:

`$ make source`

链接到构建根目录下的`dl`目录.

##3.3
#4. 定制
##4.1 定制生成的目标文件系统

#过程 错误 解决
0. host:Linux localhost.localdomain 3.5.4-1.fc17.i686.PAE #1 SMP Mon Sep 17 15:19:42 UTC 2012 i686 i686 i386 GNU/Linux
1. #error It appears you have defined _FILE_OFFSET_BITS=64. Unfortunately, uClibc was built without large file support enabled. 不知道
2. 使用mini2440_defconfig默认配置
