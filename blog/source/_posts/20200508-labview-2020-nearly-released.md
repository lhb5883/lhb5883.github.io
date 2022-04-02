---
title: 20200508-labview-2020-nearly-released
date: 2020-05-08 18:19:44
tags:
---

# LabVIEW 2020 新特性

## 社区版简介教程

Getting Started with LabVIEW 2020 Community Edition

https://learn.ni.com/training/resources/1407/getting-started-with-labview-2020-community-edition

https://learn.ni.com/training/resources/1407/courses/11523/take?locale=en_US

 

新出社区版，免费非商业使用，不能打包EXE。

支持Linx工具包，支持树莓派等Target

https://ekerry.wordpress.com/2019/11/20/introducing-labview-2020-community-edition-beta-free-for-non-commercial-use/

原来的Home版被Community取代

## 新特性 

对类的增强，可以显示多重继承了。

增加NI Web Server同时维护Application Web Server。

打包增加了对SystemLink的优化。

其他都是细节增强，

比如很多窗口界面可以调整大小。

错误窗口优化了层级关系等等

断线只清理有问题的部分。

VI的增改主要是增加了

NI Web Server相关的部分，还有加密和哈希的VI。



PS：

另外发现一个NI平台软件包2019Fall 32bit版本（对应LabVIEW 2019 SP1 32bit）下载的问题，每次下载下来的hash值都不一样，和NI官方hash对比也不一样，安装时会报安装包损坏。

用文件比较工具对比，发现集中在visa驱动部分，用64bit的镜像文件里面的同名文件替换后可以正常工作。