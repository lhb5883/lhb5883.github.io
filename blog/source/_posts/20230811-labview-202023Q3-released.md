---
title: 20230811-labview-202023Q3-released
date: 2023-08-11 18:34:46
tags:
---

# LabVIEW 2023Q3新特性
NI发布了LabVIEW 2023Q3，主要的新特性就是以下几点
第一个是等了很久的程序框图支持缩放，不过对字体的处理感觉不是很好
第二个是正在连出的连线左键双击快速创建控件，右键弹出快捷菜单，之前从右键移到二级菜单，如今终于回归了。
第三个是选中快速替换。
第四个是高亮执行可以选择速度了，长按高亮执行按钮可以在四种速度之间选择。

## macOS下原生支持ARM CPU
不过这些新特性不是我最想聊的，我最感兴趣的是在Apple的macOS平台上终于原生支持M系列ARM CPU了，无需x86转译，并且驱动也已经移植了NI VISA，也可以原生支持ARM CPU了。这个时候可以畅想一下未来的Apple生产线测试设备可能是什么样的。

之前查到Apple要求所有生产测试环节一定要运行在MacOS平台之上。
Refhttps://www.zhihu.com/question/545108671/answer/2720242493
LabVIEW在这方面确实会有一定的优势，毕竟1.0的时候就是诞生在Macintosh平台上，后续的LabVIEW也一直有macOS平台的对应软件。

## 首先我们回顾一下Intel Mac时代，我们的选择有哪些？

对于需要硬件参与的测试设备，很重要的一点就是驱动支持，mac下主要就是DAQmx Base和NI Visa，可以使用M系列或者E系列的数据采集卡以及传统的台式仪器来开发测试系统。

DAQmx base最新版本是15.0，最高支持到OS X 10.14，所以最新的刨丝器Mac Pro 2019是用不了的，老款的Mac Pro垃圾桶是没什么扩展性的，显卡都是专门定制过的，更老的Mac Pro基本上是电子古董了。

用iMac或者Mac Mini的雷电接口连接NI的雷电 MXI机箱PXIe 1090就更不用想了，NI PXI Platform Service是没有OS X版的。

综合下来能用USB M系列数据采集卡（DAQmx Base）+LXI的台式仪器（NI VISA）就是这个测试系统基本构成了，上位机可以选择能装OS X 10.14以下的Intel iMac或者Mac Mini，性能需求特别高的也可以选Mac Pro，不过也就是垃圾桶，不见得就比iMac强。

如果稍微放松一点，允许使用双系统，那么上位机装Windows，就可以使用MXI连接PXI机箱，那么基本上所有的PXI板卡都可以选型和传统的测试设备其实区别不大。

## 如果未来Apple强行要求所有测试设备使用M1设备来开发，又有什么选择呢？
目前来看只能使用传统的台式仪器来搭建测试系统，梦回八十年代LabVIEW刚刚诞生的年代。

不过我要说不过了，台式仪器的操作系统Apple可没法限制，例如示波器的操作系统，有些是定制的Linux，有些是Windows For Embeded，那么我配一个下位机，装个WES的Windows是不是也可以擦边呢？

哪怕不用Windows，就用Linux RT，开发好RTEXE之后，定一个通讯协议或者就用VI Server，在上位机的Mac上用LabVIEW开发一个测试软件似乎也是可行的？

## 稍微展望一下未来，Apple生态下的测试系统可能会是什么样的？

展望未来，一种可能是NI出了适配macOS的DAQmx，这样就可以在M2的Mac Pro上使用PCIe的数采卡了，不过以NI停产绝大部分非PXIe的趋势，应该是不太可能了。

另一种是NI的驱动完善gRPC接口，LabVIEW通过gRPC接口从M系列ARM CPU的MAC上远程调用Linux RT下位机的板卡，这样板卡的选型也能更丰富一些

## 小小的总结
其实从操作系统的演进历史来看，硬件驱动的开发也是越来越复杂，并且限制越来越多的，DOS时代只要有中断和内存映射的地址就可以直接操作硬件，NT时代就有了WDDM，区分了Kernel驱动和User驱动，Vista时代更是有了驱动强制签名认证，Windows 10有了UWP驱动，系统封装的越来越完善。对于OS X也是类似，Kext内核扩展驱动也是增加了签名认证，并且现在系统有了SIP系统完整性保护System Integrity Protection。

未来如何达成系统方便性和安全性以及扩展性的平衡，只能等待厂家，开发商，用户三者达成新的博弈平衡了。