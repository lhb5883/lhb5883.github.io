---
title: 流盘备忘录(6)-程序架构
id: 16
categories:
  - Uncategorized
date: 2009-12-05 10:00:37
tags:
---

<div id="msgcns!866B8F96A2761BBE!1437" class="bvMsg">

并行执行

采集和保存大量数据对计算机内存和CPU占用率都很高，如果使用单循环顺序结构很容易将CPU超载,所以我们有必要使用数据队列。

NI的RF流盘例程：

![RF Streaming](http://lhb5883.files.wordpress.com/2009/12/rfstreaming4.png?w=300 "RF Streaming") 

一个比较合理的架构是使用采集-送入队列 同时并行取出队列-流盘，可以较为充分的利用双核CPU。

完成之后再提取数据进行处理。

对于使用DAQmx 9.0和LabVIEW2009平台，我们还有一个更优秀的选择：使用DAQmx TDMS2.0集成流盘

![TDMS Streaming](http://lhb5883.files.wordpress.com/2009/12/tdmsstreaming2.png?w=300 "TDMS Streaming") 

这个API的好处是效率更高编程更简单，而且占用系统资源更少，直接由DAQ DMA到硬盘。而且最高速度可达1.8GBS/s

需要注意这个VI在Log模式效率最高，但是还需要读取数据做其他处理的话要选Log and Read。

![image](http://lhb5883.files.wordpress.com/2009/12/image200b3dd1c.png?w=90 "image") 

存好的文件就是标准的TDMS2.0文件。
  </div>