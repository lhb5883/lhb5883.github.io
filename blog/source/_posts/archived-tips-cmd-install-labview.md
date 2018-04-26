---
title: 快速安装LabVIEW
id: 7
categories:
  - LabVIEW
date: 2010-03-25 10:24:31
tags:
---

<div id="msgcns!866B8F96A2761BBE!1513" class="bvMsg">

通常我们安装LabVIEW最常干的事情就是不停点的下一步，然后等进度条，然后再不停的点下一步，再等待进度条，最后重启。

[![image](http://lhb5883.files.wordpress.com/2010/03/image5b25d1b50e68c.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b25d1b50e68c.png) [![image](http://lhb5883.files.wordpress.com/2010/03/image5b55d7c0a2bb9.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b55d7c0a2bb9.png) [![image](http://lhb5883.files.wordpress.com/2010/03/image5b85d26a1f898.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b85d26a1f898.png) [![image](http://lhb5883.files.wordpress.com/2010/03/image5b115d135d2dfa.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b115d135d2dfa.png) [![image](http://lhb5883.files.wordpress.com/2010/03/image5b145d2c18670b.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b145d2c18670b.png) [![image](http://lhb5883.files.wordpress.com/2010/03/image5b175d3c6fcac5.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b175d3c6fcac5.png) 

其实LabVIEW是支持命令行安装的

在CMD里面运行SETUP.EXE加上不同的参数就可以实现快速安装，例如下面这条就是快速安装LabVIEW到C盘并且装完不重启

D:NI SoftwareLabVIEW 2009 SP1LabVIEW 2009 Service Pack 1 32-bit&gt;setup.exe /qb /acceptlicenses yes /disableNotificationCheck /r:n

一旦运行就直接开始扫进度条

[![image](http://lhb5883.files.wordpress.com/2010/03/image5b205d2a3315d1.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b205d2a3315d1.png) 

一个更简单的办法是创建Setup.exe的快捷方式，然后再目标后面直接加上 /qb /acceptlicenses yes /disableNotificationCheck /r:n

[![image](http://lhb5883.files.wordpress.com/2010/03/image5b245d.png?w=212 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b245d.png) 

这样可以减少我们鼠标点击的次数…

最省事的办法还是建立一个批处理文件，批量安装多个软件~

[![image](http://lhb5883.files.wordpress.com/2010/03/image5b285d.png?w=288 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b285d.png)
  </div>