---
title: '[火星技巧]如何删除LabVIEW VI 程序框图？'
id: 10
categories:
  - LabVIEW
date: 2009-12-29 07:21:25
tags:
---

<div id="msgcns!866B8F96A2761BBE!1465" class="bvMsg">

我们为了保护代码，比较常用的办法有以下几个：

1。框图混淆：这个是最简单的办法

![LabVIEW diagram protect](https://aftv2q.bay.livefilestore.com/y1mW78VLyOAk-HYGJzedM__H9TNoOvHktwgiyEoe3U5guxLvzYvMHV5_7CIHqGgPO5tqsdJwG6oIhjNC-zuB6Boe_QVFk2whDyHTYP53qWOsPwJ5z2wDSMn5eSUFWCjb_wqV0K7U11fnfs39h6pIkYC8g/LabVIEW diagram protect[5].png "LabVIEW diagram protect")

不过随着LabVIEW2009的一键框图整理就没有什么意义了。

2。加密：缺点是如果获得密码还能被修改 

![image](http://lhb5883.files.wordpress.com/2009/12/image5b25d634ce5d3.png?w=300 "image") 

3。编译为EXE：无法修改，但是也无法被调用。

![image](http://lhb5883.files.wordpress.com/2009/12/image5b55d69e2346d.png?w=300 "image") 

4。删除程序框图：无法编辑但是可以被同版本LabVIEW调用。

具体操作步骤：

1。新建工程

![image](http://lhb5883.files.wordpress.com/2009/12/image5b85d3f135178.png?w=241 "image") 

2。新建空白主VI

![image](http://lhb5883.files.wordpress.com/2009/12/image5b115d.png?w=241 "image") 

3。添加被处理VI 

![image](http://lhb5883.files.wordpress.com/2009/12/image5b175d14f9367b.png?w=281 "image")  

4。创建应用程序，添加启动VI和支持VI

![image](http://lhb5883.files.wordpress.com/2009/12/image5b205d.png?w=300 "image")

5。源文件设置：**<font color="#ff0000">被处理VI选择目标到支持目录，还可以配置是否需要删除前面板和程序框图</font>**

![image](http://lhb5883.files.wordpress.com/2009/12/image5b235d2b96af1c.png?w=300 "image")  

6。生成程序

![image](http://lhb5883.files.wordpress.com/2009/12/image5b265d.png?w=300 "image") 

该VI可以被打开和调用但是无法被编辑，也无法察看程序框图。

![image](http://lhb5883.files.wordpress.com/2009/12/image5b295d.png?w=300 "image")
  </div>