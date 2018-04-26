---
title: 流盘备忘录(4)-存盘API
id: 12
categories:
  - Uncategorized
date: 2009-12-02 07:36:29
tags:
---

<div id="msgcns!866B8F96A2761BBE!1426" class="bvMsg">

存盘接口

Windows写入文件有两种形式缓冲和非缓冲

[http://msdn.microsoft.com/en-us/library/aa365747(VS.85).aspx](http://msdn.microsoft.com/en-us/library/aa365747(VS.85).aspx)

缓冲模式是Windows自动分配缓冲区将数据分割到硬盘的每个簇大小以便写入，而非缓冲模式是有我们程序员进行缓冲区 的分配，可以任意指定大小。（这个任意并不是绝对的，必须要是硬盘簇的整数倍）

XP系统默认的缓冲区应该不是很大，在Copy文件时效率比Windows7要低一些，而在我们操作巨型的文件时至少要4MB以上的缓冲区才能发挥出最大效能。

如下图所示，block size越大数据流盘速度就相对越快，读盘反而是缓冲区较小时效率较高。不过这张图使用的是RAMDISK，数据只能供参考，使用硬盘时可以再行测试。

[![image](https://aftv2q.bay.livefilestore.com/y1mmJSZHqeg1_dNBpTc6Djg73HIE-DyBZiWejBXbE3B9Jg78ilPCO3f9Xmx9x4CMddw6Q-paX_XTIcQ2Y3E7yOi0lewNzyomXKE4vp9-n7JchgCiE17yaEMP8Ux_HMMH1CrCCuTNwtubzvN43O_65mUKA/image_thumb 763FDADC.png "image")](https://aftv2q.bay.livefilestore.com/y1mat4peCvjmEMxPILOBL4FVkwlcJIh2zKzqf4tHnaYy-Cew0asruMV-q8nQPl_ycWqG4NnNlPfNpfRIBJ9IOQ0FtLE9DdHhvkrF-y1OrOnoaqSCiMQBTGsv6LV15isGY20RnyhK6l729eJo_2xqmZnBw/image25.png) 

在LabVIEW 2009里面支持非缓冲格式流盘的有TDMS，BINARY和Win32APIVIs三种

![image](https://aftv2q.bay.livefilestore.com/y1m4CV566wf7PJgi97WlOxgGH0Wo06tB9RxB7f_jJOr7OXVIePxxEWGB_1CTjM1sMQ-1TF7lxUUg7HOMqixnY_6dmjJASUsBc3AcILPmT_T6wrsnNMQmbcPL2zwdp9vechREimzqj5lR8v7ApbXeOu09Q/image[5] 0B448D74.png "image") 

LabVIEW 2009 TDMS

[![TDMS](http://lhb5883.files.wordpress.com/2009/12/tdms6.png?w=300 "TDMS")](http://lhb5883.files.wordpress.com/2009/12/tdms6.png)

Lab VIEW 2009 Binary

[![LabVIEW 2009](http://lhb5883.files.wordpress.com/2009/12/labview20094.png?w=300 "LabVIEW 2009")](http://lhb5883.files.wordpress.com/2009/12/labview20094.png) 

Win32API

[![win32](http://lhb5883.files.wordpress.com/2009/12/win324.png?w=300 "win32")](http://lhb5883.files.wordpress.com/2009/12/win324.png) 

这三种接口效率如何我们用RAMDISK分配一个内存盘以测试API本身的性能。

[![image](http://lhb5883.files.wordpress.com/2009/12/image27.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/12/image27.png) 

[![image](http://lhb5883.files.wordpress.com/2009/12/image29.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/12/image29.png) 

[![image](http://lhb5883.files.wordpress.com/2009/12/image314f2cef3a.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/12/image314f2cef3a.png) 

[![image](http://lhb5883.files.wordpress.com/2009/12/image33.png?w=277 "image")](http://lhb5883.files.wordpress.com/2009/12/image33.png) 

结果： TDMS 153.2MB/s LabVIEW2009 Bin 497MB/s Win32APIVIs 515.9MB/s

分析 因为三种API流盘的目标都是内存，数据量也相等，所以性能的差别应该是API本身造成的，观察CPU占用也可以看到TDMS最高，LabVIEW2009 bin和Win32基本持平，可见写入函数过于复杂也会影响存盘效率。
  </div>