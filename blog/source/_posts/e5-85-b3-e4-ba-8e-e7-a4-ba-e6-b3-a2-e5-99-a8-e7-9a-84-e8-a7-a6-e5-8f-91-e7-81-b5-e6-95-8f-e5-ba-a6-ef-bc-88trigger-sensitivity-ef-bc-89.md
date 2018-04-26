---
title: 关于示波器的触发灵敏度（Trigger Sensitivity）
id: 21
categories:
  - Computers and Internet
date: 2009-09-15 06:19:01
tags:
---

<div id="msgcns!866B8F96A2761BBE!1381" class="bvMsg">

示波器板卡有一项参数叫Edge Trigger Sensitivity

![NI PXI/PCI-5152 Specifications（P11）](http://lhb5883.files.wordpress.com/2009/09/image5b25d23274975.png?w=300 "NI PXI/PCI-5152 Specifications（P11）")

这一项指标翻译过来应该是触发敏感度，有什么意义呢？

当我们用示波器高速采集一个高频脉冲信号时，往往会混入很多噪声信号，如果没有触发敏感度，直接按边沿触发往往不能得到一个稳定的示波器图形。

![图输入200mVpp锯齿波时的情况。](http://www.ed-china.com/ARTICLE_IMAGES/200801/20080101_TM_DT_TS_27F2.JPG "图输入200mVpp锯齿波时的情况。")

触发灵敏度就是用来滤除噪声对触发的影响，使之能够正确被有效信号而非噪声触发，获得稳定波形的一个参数。

TEK网站的定义如下：

###### Trigger Sensitivity

Trigger sensitivity is a critical attribute when capturing high-speed digital signals. An oscilloscope‘s trigger sensitivity determines its ability to react to specified edge trigger conditions over a range of frequencies. The specification takes the following form: power-line hum interference. 

**Trigger System Sensitivity, Internal DC Coupled:**
0.35 div DC to 50 MHz, increasing to 1.5 div at 3 GHz
(guaranteed); 2.7 div at 4 GHz (typical)
(from TDS7404 DPO data sheet)

The oscilloscope will trigger on a signal of 0.35 divisions amplitude p-p in the range of frequencies from DC to 50 MHz. As the frequency goes beyond 50 MHz, the signal must be larger (higher in amplitude) to trigger the instrument. At 3 GHz, the signal must be at least 1.5 divisions in amplitude. Trigger sensitivity is specified with a sine wave input. <p>灵敏度
在捕获高速数字信号时，触发灵敏度是一个关键指标。示波器的触发灵敏度决定着在某个频率范围内示波器对规定边沿触发条件的反应能力。这一指标采用下述形式：电源线噪声干扰。
       触发系统灵敏度、内部DC耦合:
DC - 50 MHz, 0.35格；3 GHz时提高到1.5格(保障值); 4 GHz时2.7格 (典型值)(摘自TDS7404 DPO技术数据)
示波器将在DC到50 MHz 的频率范围内，在0.35格的p-p幅度上触发。在频率超过50MHz时，信号必须更大(幅度更高)，以触发仪器。在3 GHz时，信号的幅度必须在1.5格上。可以使用正弦波输入指定触发灵敏度。 <p>开头图中的指标就是说使用通道触发时灵敏度是满量程的10%，而使用外部触发时灵敏度是固定的0.5V峰峰值。小于灵敏度的毛刺都会被示波器忽略，不认为是触发。 <p>参考链接：

[http://www.ed-china.com/ART_8800024153_400013_500015_TS_f6dcb05a.HTM](http://www.ed-china.com/ART_8800024153_400013_500015_TS_f6dcb05a.HTM)

[http://www.tek.com/Measurement/scopes/selection/performance/trigger.html](http://www.tek.com/Measurement/scopes/selection/performance/trigger.html)

触发扫盲：

[http://www2.tek.com/cmsreplive/tirep/4394/55C-17291-2_2009.05.27.00.56.45_4394_ZH.pdf](http://www2.tek.com/cmsreplive/tirep/4394/55C-17291-2_2009.05.27.00.56.45_4394_ZH.pdf "http://www2.tek.com/cmsreplive/tirep/4394/55C-17291-2_2009.05.27.00.56.45_4394_ZH.pdf")
  </p></div>