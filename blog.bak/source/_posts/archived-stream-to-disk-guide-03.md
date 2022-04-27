---
title: 流盘备忘录(3)-数据格式
id: 13
categories:
  - Uncategorized
date: 2009-11-26 08:00:17
tags:
---

<div id="msgcns!866B8F96A2761BBE!1393" class="bvMsg">

数据保存格式注意事项

2D I32 数据换算.

以DAQmx读取为例，我们读取数据可以用以下三种格式：

![image](http://lhb5883.files.wordpress.com/2009/11/image11595a2be2.png?w=157 "image") 

![image](http://lhb5883.files.wordpress.com/2009/11/image1438466da1.png?w=177 "image") 

![image](http://lhb5883.files.wordpress.com/2009/11/image20.png?w=143 "image") 

其中I16占用内存最小，每一个采样使用2Byte内存，DBL会占用8个Byte，在采集大量数据时使用RawData可以大量减少内存和CPU的使用。

binary data格式

二进制表示的是AD芯片转换的原始信息，如何换算为电压呢？

直接 Volt=bin data/(2^ADbits)*Range理论是可行的 ，但是实际上是不准确的，因为通道还有校准信息我们没有得到。

DAQmx提供了通道的标定信息，结合多项式函数就可以简单的得出实际电压。

![convert data](http://lhb5883.files.wordpress.com/2009/11/convertdata_thumb.png?w=300 "convert data") 

交织还是非交织;

对于RawData来说，单通道的结构比较简单就是一个数组，但是多通道时读回来的还是一个1D Array，如何找出每个通道所对应的数据呢？这就牵扯到交织和非交织了。
 > ### Raw Data
> 
> Raw data is in the native format and _organization_ of the device, read directly from the device or buffer without scaling or reordering. The native format of a device can be an 8-, 16-, or 32-bit integer, signed or unsigned.  <p>If you use a different integer size than the native format of the device, one integer can contain multiple samples or one sample can stretch across multiple integers. For example, if you use 32-bit integers, but the device uses 8-bit samples, one integer contains up to four samples. If you use 8-bit integers, but the device uses 16-bit samples, a sample might require two integers. This behavior varies from device to device. Refer to your device documentation for more information.  <p>NI-DAQmx does not separate raw data into channels. It returns data in an [interleaved or non-interleaved](interleaving.html) 1D array, depending on the raw ordering of the device. Refer to your device documentation for more information.  
> 
> ### Interleaving
>  <p>Interleaved samples prioritize samples before channels, such that the array lists the first sample from every channel in the task, then the second sample from every channel, up to the last sample from every channel.  <p>Channel 0—Sample 1  <p>Channel 1—Sample 1  <p>Channel 2—Sample 1  <p>Channel 0—Sample 2  <p>Channel 1—Sample 2  <p>Channel 2—Sample 2  <p>...  <p>Channel 0—Sample _N_  <p>Channel 1—Sample _N_  <p>Channel 2—Sample _N_  <p>Non-interleaved samples prioritize channels before samples, such that the array lists all samples from the first channel in the task, then all samples from the second channel, up to all samples from the last channel.  <p>Channel 0—Sample 1  <p>Channel 0—Sample 2  <p>...  <p>Channel 0—Sample _N_  <p>Channel 1—Sample 1  <p>Channel 1—Sample 2  <p>...  <p>Channel 1—Sample _N_  <p>Channel 2—Sample 1  <p>Channel 2—Sample 2  <p>...  <p>Channel 2—Sample _N_
> </p></p></p></p></p></p></p> 

最简单的例子6124采集到的数据卡内通道是交织的，卡间又是非交织的，

一个使用两块6124每块使用2个通道连续采集每次采集3个点的数据应该如下：

Broad0CH0Sample1

Broad0CH1Sample1

Broad0CH0Sample2

Broad0CH1Sample2

Broad0CH0Sample3

Broad0CH1Sample3

Broad1CH0Sample1

Broad1CH1Sample1

Broad1CH0Sample2

Broad1CH1Sample2

Broad1CH0Sample3

Broad0CH1Sample3

Broad0CH0Sample4

Broad0CH1Sample4

Broad0CH0Sample5

Broad0CH1Sample5

Broad0CH0Sample6

Broad0CH1Sample6

Broad1CH0Sample4

Broad1CH1Sample4

Broad1CH0Sample5

Broad1CH1Sample5

Broad1CH0Sample6

Broad0CH1Sample6

抽象一下应该如下图，SampleBlock包含了所有通道这一次采集的N点

SampleBlock1 

SampleBlock2

SampleBlock3

….

然后每个SampleBlock里面包含BroadSample

Broad0sample

Broad1sample

Broadsample包含着N次采样

Sample1

Sample2

Sample3

…

SampleN

每个Sample里含有这块板卡上的通道各一个点

CH1

CH2

CH3

CH4

所以一定要分析清楚数据结构才能正确解析出各通道数据

![deInterleaving](http://lhb5883.files.wordpress.com/2009/11/deinterleaving_thumb.png?w=300 "deInterleaving")
  </div>