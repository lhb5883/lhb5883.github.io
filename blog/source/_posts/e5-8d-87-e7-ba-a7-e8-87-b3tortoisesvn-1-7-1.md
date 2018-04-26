---
title: 升级至TortoiseSVN 1.7.1
id: 258
categories:
  - LabVIEW
date: 2011-10-28 10:43:37
tags:
---

在开源界SVN是一个非常有朝气的项目，这个可以从他的版本每两周一个小版本的升级的速度就看出来。

虽然SVN 1.7出来也有一段时间了，不过一直没有太关注过，最近偶然看到SVN新版本的特性，有几项非常实用的功能和更新，所以果断更新到1.7.1。

值得注目的新特性有：

1.  数据库整合至根目录（终于解决了目录更名错乱的问题！）
2.  深度支持Windows 7。新增Windows 7库整合，界面支持Windows 7 Aero特效。
3.  客户端和服务器均向下互兼容，1.7的客户端也可以配合1.6的服务器使用。
更新要注意的问题：

1.  升级安装需要安装两次，第二次选择修复。
2.  工作副本需要升级至新版本，并且无法降级。
建议升级流程：

1.  提交所有工作。
2.  升级SVN（注意要安装一次修复一次！）
3.  重新下载或者升级工作副本。
[![image](http://lhb5883.files.wordpress.com/2011/10/image_thumb.png "image")](http://lhb5883.files.wordpress.com/2011/10/image.png)

[https://decibel.ni.com/content/groups/large-labview-application-development/blog/2010/03/29/using-subversion-svn-with-labview](https://decibel.ni.com/content/groups/large-labview-application-development/blog/2010/03/29/using-subversion-svn-with-labview)