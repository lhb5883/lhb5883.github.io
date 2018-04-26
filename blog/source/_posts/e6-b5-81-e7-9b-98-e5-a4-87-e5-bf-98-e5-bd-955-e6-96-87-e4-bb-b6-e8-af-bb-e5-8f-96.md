---
title: 流盘备忘录(5)-文件读取
id: 17
categories:
  - Uncategorized
date: 2009-12-02 08:48:04
tags:
---

<div id="msgcns!866B8F96A2761BBE!1430" class="bvMsg">

我们存好数据并不是大功告成了，我们还需要从流盘数据文件恢复各通道信号才能再做各种分析。

其中最关键的核心问题就是存盘的文件格式和数据解析。

上一篇我们已经解析了一个数据块的构成，这一篇我们来看看到底如何用LabVIEW实现：

[![LabVIEW read all channel data](http://lhb5883.files.wordpress.com/2009/12/labviewreadallchanneldata5b55d.png?w=300 "LabVIEW read all channel data")](http://lhb5883.files.wordpress.com/2009/12/labviewreadallchanneldata5b55d.png)

这个在数据量较小时姑且还可以用一用，不过要想更灵活的解析出各个通道数据，还需要推导出采样在文件中的位置公式。

我们需要的参数有

1.  通道所在的板卡编号 BoardID（从0开始）  <li>通道在板卡上的编号 ChannelID（从0开始）  <li>采样点的编号 SampleNum  <li>一共有多少板卡 BoardNumber  <li>每板卡使用几个通道 ChannelNumber  <li>每个数据块每通道的采样点 SampleperChannel  <li>每个采样占用的字节 SampleByte 

我们需要得出的参数：

1.  我们所需采样点在文件中的位置 SamplePosition 

SamplePosition=

&#123;

(SampleNum/SampleperChannel)*SampleperChannel*BoardNumber*ChannelNumber 数据块偏移
+
BoardID*SampleperChannel*ChannelNumber 板卡偏移
+
(mod(SampleNum,SampleperChannel))*ChannelNumber 采样偏移
+
ChannelID 通道偏移

&#125;*SampleByte

![image](https://aftv2q.bay.livefilestore.com/y1m7Q8U7w8Oul572fCc-_Iku3gROg3G7UYbKwGiqI2yE0L4fjrmcVZuhmWS8I_kyuyLgPbV2QQcxkZd0Srka7RHfHzq8l7eACtuMnkkkKmK2Awa3r1Bo_W0HIEiuMGGpOB--GGNseEjOzcx6xRVSSLawA/image[5].png "image") 

另外要注意的是偏移量最好用U64，I32最多能寻址2GB，大于2GB就会溢出。

有了这个公式再配合设置偏移量，就可以很方便的取出每个通道的数据了。

其他要注意的是如果使用Win32API，那么读取数据的高低位是Windows格式的Little Endian而不是LabVIEW通常的Big Endian。

![image](https://aftv2q.bay.livefilestore.com/y1mIS2FZksrhqxtsgC3tXJ_mDvez4ehbPJQh2c4DopAAVhWZx9aFCtp5rWsN7AX-LTKlTQ_THRfpctxWDI8ybrE5bq3TmZA7DELe4rdb84tsO3lSinX9Q7dix3gBzcWOBZsNy1qAbfkMacqMZvik6bJ-A/image[3] 4EFCFDF4.png "image") 

[](https://aftv2q.bay.livefilestore.com/y1m_jcU-aepq8aD9tZ4T2IdyzWPI43xpwNF3eQWd6zishWaHJyvXioh4tjQLDf882YIIUQszfI1azwrP1t1gec6R-lUwUOSyGE-3KzE_IBtQO2LP9tGCSpkOLg2J-zUNcXzJPuzEYtFrBIIfGPVlpoVmg/LabVIEW read all channel data[5].png)
  </div>