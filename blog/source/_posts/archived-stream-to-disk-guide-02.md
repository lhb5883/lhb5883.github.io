---
title: 流盘备忘录(2)-软件选择
id: 14
categories:
  - Uncategorized
date: 2009-11-26 07:41:21
tags:
---

<div id="msgcns!866B8F96A2761BBE!1392" class="bvMsg">

对于流盘来说软件也是很重要的,其中会影响到我们流盘性能的有以下几点:

驱动是否高效

是否成功启用了DMA传输采集到的数据以减少系统资源占用。以NI的数据采集卡为例，传统DAQ不使用DMA和中断的方式采集数据其CPU占用率长时间飙升在100%，使用DAQmx默认使用DMA方式可以大大减小CPU的占用率。

软件架构是否合理

我们需要实现的三个主要任务：采集、处理、保存占用率合理分配，数据存储格式应该在保证精度的前提下减小内存占用。

存盘API性能

系统处理文件操作的API分配的缓冲区太小，在读写大文件上性能较低。

关键点：

1 驱动一定要支持DMA,减小CPU占用.提供RAWdata格式和转换公式,减小数据内存占用

2 能否合适的将负载分配到各个CPU上.支持并行和多线程

3 支持底层的无缓冲模式API,避免软件流盘速度瓶颈.

解决方案

1 使用NI DAQmx驱动和NI MI驱动，并启用DMA。

![image](http://lhb5883.files.wordpress.com/2009/11/image24cd46edb.png?w=185 "image") ![image](http://lhb5883.files.wordpress.com/2009/11/image5b65d6a92a742.png?w=32 "image") 

采集原始数据减小内存占用

![image](http://lhb5883.files.wordpress.com/2009/11/image852bb2442.png?w=77 "image") ![image](http://lhb5883.files.wordpress.com/2009/11/image1157e9bf59.png?w=99 "image") ![image](http://lhb5883.files.wordpress.com/2009/11/image5b35d1ff72f9c.png?w=52 "image") 

2 使用LabVIEW或者其他多线程开发软件，启用并行循环和队列。

 ![RF Streaming](http://lhb5883.files.wordpress.com/2009/11/rfstreaming_thumb5b15d.png?w=300 "RF Streaming") 

3 使用Win32API，直接调用底层函数并分配较大的缓冲区

![image](http://lhb5883.files.wordpress.com/2009/11/image14135548b4.png?w=32 "image")
 <p>C++

    BOOL WINAPI WriteFile(
      __in         HANDLE _hFile_,
      __in         LPCVOID _lpBuffer_,
      __in         DWORD _nNumberOfBytesToWrite_,
      __out_opt    LPDWORD _lpNumberOfBytesWritten_,
      __inout_opt  LPOVERLAPPED _lpOverlapped_
    );
  </div>