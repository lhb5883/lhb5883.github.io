---
title: 批量安装LabVIEW及组件
id: 6
categories:
  - LabVIEW
date: 2010-03-26 03:54:47
tags:
---

<div id="msgcns!866B8F96A2761BBE!1520" class="bvMsg">

有了命令行我们只不过节约了几下鼠标,还要安装好一个组件之后再手动装下一个组件,还是很麻烦,有没有什么省事的办法呢?

当然有,我们有请批处理文件(*.bat)出场.

[![image](https://aftv2q.bay.livefilestore.com/y1mqqNVZcgJPai7kLPfP-bwMXNiRj29p8OYhJkPI15R4vn-ro4qQ2lmU7LvHK1j8vfdh80QCLBLHUUlNPZ8CGUSbKVIA0-GWa2ehglraOPJmcCneWxwzrX6qOYGMC-_ATAVTbAGb9Tm6YnLhpCHrvT4lA/image_thumb[3] 61095F84.png "image")](https://aftv2q.bay.livefilestore.com/y1mUGyPv86VpDqpCvF1g-XtKjzFES9Fqx3qayyX_rzmMyemnavCeqy0POzZbplHgpdqKAI61smPZYESdVKW-SfCMFM9yeerGRnxIiF_bCWau4I1wbRhbkmnZ9jec-eHQ5Xc8TrnqoYdBlfWAzBMTccypg/image[7].png) 

[![image](https://aftv2q.bay.livefilestore.com/y1mi-lnu06Lw7420S6HuMj8vWvDELiUrYj5iFZh4uw6XG8ORN_jYecm_QDrc07hu3RGxH1HiXUe6FW4TdMn3h6mhcfBrgK-V3dyrx033bkzAzVBJlOr23tK3rI6MB8wA1ukQGmrQh3218WNIc-kGtsWaw/image_thumb[5] 2B50062B.png "image")](https://aftv2q.bay.livefilestore.com/y1mvtOis4jV9Le2-VIxUzE8D0cQwamCCNhUO-ndQNg3MCQ5ElsW3S70crQNR2pKO9BgeMwPvD8QNK3VYn2isBius6dsvpwOoV9sIEVwNuy8T8wC246WqxJpAudZsF1O0INPxzTdfRK85AWTO7BTzcLePg/image[11] 0C99DDE7.png) 

对于上面这种情形，我们只要建立一个文本文件，输入以下内容，命名为Install.bat双击运行就可以一次安装LabVIEW2009SP1，实时，控制设计仿真等软件： <p>&quot;o:NI SoftwareLabVIEW 2009 SP1LabVIEW 2009 Service Pack 1 32-bitsetup.exe&quot; /qb /acceptlicenses yes /disableNotificationCheck /r:n
&quot;o:NI SoftwareLabVIEW 2009 SP1LabVIEW 2009 SP1 Real-Time Modulesetup.exe&quot; /qb /acceptlicenses yes /disableNotificationCheck /r:n
&quot;o:NI SoftwareLabVIEW 2009 SP1LabVIEW 2009 SP1 Control Design and Simulation Modulesetup.exe&quot; /qb /acceptlicenses yes /disableNotificationCheck /r:n <p>假如安装包放在其它计算机的共享里面呢？可以使用命令行把共享映射到本地驱动器： <p>net use o: <a>\pansinoagtreadonly</a> <p>[![image](http://lhb5883.files.wordpress.com/2010/03/image5b155d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/03/image5b155d.png)  <p>这样我们就可以让他自己安装，而不需要我们操心了。   
</div>