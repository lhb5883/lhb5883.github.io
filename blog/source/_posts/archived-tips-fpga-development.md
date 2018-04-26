---
title: 如何加速FPGA开发？
id: 30
categories:
  - Uncategorized
date: 2009-02-16 06:10:44
tags:
---

<div id="msgcns!866B8F96A2761BBE!1185" class="bvMsg">

NI LabVIEW FPGA模块提供了一个非常方便的接口供我们以LabVIEW图形化的方式开发FPGA程序，不过也有令人困扰的问题就是LabVIEW FPGA代码编译的速度较慢，如果机器的配置不够高就是一件折磨人的事情。 <p>所以今天给大家介绍几个小技巧： <p>1\. IPnet <p>对于LabVIEW开发者，最常用的就是范例查找器这个工具，俗话说得好：“有范例，无问题。” <p>对于FPGA，还有一个非常好的工具： 

### LabVIEW FPGA IPNET
 <p>[http://zone.ni.com/devzone/cda/tut/p/id/6870](http://zone.ni.com/devzone/cda/tut/p/id/6870 "http://zone.ni.com/devzone/cda/tut/p/id/6870") > <p>LabVIEW FPGA IPNET是您浏览、领会和下载LabVIEW FPGA函数或IP（知识产权）的一站式资源中心。下表是从LabVIEW FPGA函数调色板、NI内部开发人员和LabVIEW FPGA社区收集的FPGA IP与范例的集合。您应当使用这一资源中心，以获取您的应用所需的IP、下载范例以帮助掌握编程技术和深入探究LabVIEW FPGA平台所提供的IP。除了探究这里所提供的资源外，您也可以通过点击下面的链接，为LabVIEW社区共享您的LabVIEW FPGA IP或者提交您对现有IP的更新。 <p>IP是知识产权的缩写，这里就是指NI FPGA的算法。 <p>2.LabVIEW验证 <p>当我们自己写好一个算法或者我们找到了别人写好的IP以后，为了减少编译后在返工的情况，我们可以在LabVIEW里面验证一下算法是否有逻辑问题。 <p>A：在My Computer新建一个VI把FPGA算法复制进去，然后在My Computer下调试。 <p>B：在建好的VI下修改程序运行的位置。 <p>[![image](https://aftv2q.bay.livefilestore.com/y1mVCBaze_B73nnXu9lsLJpGKuFuUQK1iPmaQjTGIOPRkBGIelNyBG-V47Clnc88V7vkwAFyGV06S0baTjnrPC0gwHv5rW0UKOKmGzZXZ87x_Nmy8CvtRAFbTiNP1CuQ6l8cs-nW8JumGA/image_thumb[1].png "image")](https://aftv2q.bay.livefilestore.com/y1m16CiQX4LAsE9oz0_nT9oAPGaxircpCKDunowiDEkwRpRA8a_dtd1ahoztEJzH2fLqq5VONClJxbx-wJJMajnGrCfGRRqIDe4wDsKqggbfhOSFMOWLVfPRm--pW4RPUSotvSRaw6JaIs/image[3].png)  <p>3.设置Compile Server： <p>LabVIEW FPGA编译过程是比较长的，并且速度和计算机配置有关，我们可以在一台机器上开发，另一台机器上编译，这样可以节约时间。 <p>首先在服务器端打开compileServer，并确保防火墙开放96端口或者关闭防火墙， <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b65d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b65d.png) [![image](http://lhb5883.files.wordpress.com/2009/02/image5b175d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b175d.png)  <p>然后在客户端LabVIEW工具菜单下打开FPGA Module Option，点击Configure按钮，在Machine下输入服务器IP地址，点击OK保存，这样在编译FPGA时就会调用服务器进行。 <p> <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b125d.png?w=279 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b125d.png) [![image](http://lhb5883.files.wordpress.com/2009/02/image5b165d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b165d.png)  <p>  <p>附 FPGA代码的编译过程： <p>首先将LabVIEW 程序框图转换为临时文件，然后传输到编译服务器生成和优化VHDL代码，最后编译为bitfile供下载到FPGA执行。 <p>其中最耗时就是LabVIEW生成VHDL这一步，因为从图形化代码到逻辑电路关系的翻译需要大量的运算，除此之外还要为FPGA芯片优化，提高执行效率，这样就导致要花费较多的时间。  
</p></p></p></div>