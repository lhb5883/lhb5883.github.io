---
title: cRIO摧残记（中）——RealTime篇
id: 39
categories:
  - Uncategorized
date: 2008-04-08 11:13:22
tags:
---

<div id="msgcns!866B8F96A2761BBE!751" class="bvMsg">

上次我们提到cRIO是由RT控制器、FPGA、模块三部分构成的，今天我们要研究的是cRIO的RT控制器的定时精度。

在LabVIEW的RT例程里面专门有一个benchmark程序，可以用来测试代码的执行时间。

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhM1bRQ2Yn6fZwa_wtmNQsnBZDLygUIyYAvrSxBy6VSympC5KhNA9pIoAV1wXkd92WZMrptQoVIgO21XY12e6mwj?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr-1y4meOuwAT2PdIaBVzeqAhZZIl4Se-oWsO6Wo3ImpemAS0dTZHaK8QHxdDhf2npniS8dH-X5oHQ?PARTNER=WRITER) 

今天我们要测试的是RT的wait函数：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxIAxqp-1KTfCEOVMfgm9opFQ_VPkg-8pT8auEqqpewRNh9pY3GPmqX96wQMaUAkp-Iov0sCBXJ8a346UZuvKFG?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyfcCWmMOlLCQ9SOzeX1g1fttzRuey7W4tvnerY6PiRYaAgCOGQ-6EX3vxuuLYOY1rNjJVANnQPzitbJnrtaK-h?PARTNER=WRITER) 

Wait函数有三种定时单位可以选择：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpy-CA3WeV1N4Ktwc7tRyMgO0CO36qkW63w8S-Wh82Ee9G8UnZfAcxLQM6iQM9qBQdKDXuCoOd8mDRrH3teKVmkH?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxDq3PvOetL-QLdCmPU-Sn_uXxfFytATTilMdHKkyjPg6LoY5ryVza7_mGCTRoLEng4wB6teMmFXfDUuY0-52PF?PARTNER=WRITER)

mSec毫秒：这个和一般非Rt的程序里面等待函数用法是一样的

uSec微秒：顾名思义，以微秒为单位定时

Ticks时钟：这个比较诡异，根据下面的实验是以纳秒为单位定时。

下面就是实验的截图，点击可以看大图，图中横轴代表定时的时间，纵轴代表测得的延时时间：
 <table cellspacing="0" cellpadding="2" width="400" border="1"> <tbody> <tr> <td valign="top" width="100">Ticks方式：</td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td></tr> <tr> <td valign="top" width="100">100</td> <td valign="top" width="100">1000</td> <td valign="top" width="100">2000</td> <td valign="top" width="100">2500</td></tr> <tr> <td valign="top" width="100">[![tick 100ns](http://by2.storage.msn.com/y1p8NjIsGi7lpxEZVVq6Ms4vkymeJA9gbZzDYg-8OQRqUUXDnJ1JU2aANlV6Qe9XqAj0lKocDElQiP4QAi3K2qoFMmn9afYr834?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhNdYPoQF__zVl9jVlpAGB0xvstaxYtjhFsuu66s10ugT7ZzM2Na_N7tfG9JBH2K-OK-M0BCStsW7UKlawIW1fiW?PARTNER=WRITER)</td> <td valign="top" width="100">[![tick 1000ns](http://by2.storage.msn.com/y1p8NjIsGi7lpzltceUdA8pVKhqcDNEKO3ReUlrjoA870Vw46Mue8R5Dtl4t00v7VNaLZAv34n04rndSSGVanWJeNs2zAAT3HC3?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhN_lAhLLVXxX8tTnz4Aug1QyJumYzVBWBTB2If5Y1DWYLeTGqmnS1Y-BkgRFIGLGVKnf09JOQCm6FGnQm5HlmAS?PARTNER=WRITER) </td> <td valign="top" width="100">[![tick 2000ns](http://by2.storage.msn.com/y1p8NjIsGi7lpzD0Gpwjvz6Q6QmbkyqzJpFM3wXwwZC_moCditymrPUyUrJW-g_fb0_CFfL7J9O_VtOhZnEB8IJIti6ZnBhf5fs?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMkenl1eYt-wG9wegJDUW56QNA3BM1UY3S8Z-zWz3RVZQ6Ole7EzQFCvuL_2AtmcjLNZcJv_o3Ft6nEBLv_TqUI?PARTNER=WRITER) </td> <td valign="top" width="100">[![tick 2500ns](http://by2.storage.msn.com/y1p8NjIsGi7lpwOrjGOm1aDOb7RQP6PFoKM0mEDH4Cr54L6_LtMpEtPp7Br_f1C53aJsTPij-EGB-n4L9KKQcUj0ZJY5Y1ovqQm?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOjKZQJYG09JmkNRVDv4gkXNyn-VMxcIT6V9C1xWJQnxvUNqCJ0ycSAYPippKIs-9I_YbBigu5TfRSqL3LbsuOP?PARTNER=WRITER) </td></tr> <tr> <td valign="top" width="100">uSec方式：</td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td></tr> <tr> <td valign="top" width="100"> </td> <td valign="top" width="100">1us</td> <td valign="top" width="100">2us</td> <td valign="top" width="100">3us</td></tr> <tr> <td valign="top" width="100"> </td> <td valign="top" width="100">[![uSec 1us](http://by2.storage.msn.com/y1p8NjIsGi7lpwxA_7glJKlosjtAkGvsxZbTU4srQ1kwHlsHxC-kHdicLqAOn7W1jYA6TV5wZj-2pXitvr-4XP5LtImgzNmuEW5?PARTNER=WRITER) ](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhN0SSHjgkBl6p_fL8lYcmBggZBEvVbZHthF7_mr8kSWAPHqrU34MaxSliInIn2bmCJfFBF9C9GCP2o36TganMZx?PARTNER=WRITER)</td> <td valign="top" width="100">[![uSec 2us](http://by2.storage.msn.com/y1p8NjIsGi7lpx82eOyflJuKsCNnjH2WPaC5V0OGDNrSPQPV2uAUx4htz_hZbHyBGBgKdQ0vF9OYUCkQo2uE-otaL-1wdBn2bnN?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhM4dQCbUJxgeITDyr31Wu-NllXSeATleh-znVAjqvwyv1SMlSu-VfN298yUSLRZMVA7EmWs7IrvNQP63lVk-dDj?PARTNER=WRITER)</td> <td valign="top" width="100">![uSec 3us](http://by2.storage.msn.com/y1p8NjIsGi7lpxrGzTWBj4XAkDz2VlibjLAgzFYiH2R51i0-vF0qclEsHXfE2TllzS2pl0WKDU3dXa0oFln9ljANaWQ0hxcEnTW?PARTNER=WRITER)</td></tr></tbody></table> 

可以得出的几个结论：

1 Ticks的计时单位是纳秒

2 cRIO的定时间隔在20us下是不准确的，在20us以上基本上可以认为是线性的。
 <table cellspacing="0" cellpadding="2" width="402" border="1"> <tbody> <tr> <td valign="top" width="100">Ticks方式：</td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td></tr> <tr> <td valign="top" width="100">100</td> <td valign="top" width="100">1000</td> <td valign="top" width="100">2000</td> <td valign="top" width="100">2500</td></tr> <tr> <td valign="top" width="100">21000ns之后可以认为是线性的</td> <td valign="top" width="100">22000ns</td> <td valign="top" width="100">22000ns</td> <td valign="top" width="100">20000ns</td></tr> <tr> <td valign="top" width="100">uSec方式：</td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td> <td valign="top" width="100"> </td></tr> <tr> <td valign="top" width="100"> </td> <td valign="top" width="100">1us</td> <td valign="top" width="100">2us</td> <td valign="top" width="100">3us</td></tr> <tr> <td valign="top" width="100"> </td> <td valign="top" width="100">22us</td> <td valign="top" width="100">16us</td> <td valign="top" width="100">18us</td></tr></tbody></table> 

3 这一点是个人的猜想，仅供参考：20us以上的定时也不是完全线形的，有可能是因为cRIO的RT时钟间隔造成的，
</div>