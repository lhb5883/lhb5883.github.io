---
title: cFP摧残指南——串口篇
id: 35
categories:
  - Uncategorized
date: 2008-05-14 01:07:22
tags:
---

<div id="msgcns!866B8F96A2761BBE!954" class="bvMsg">

大家好，继前一段的[cRIO摧残系列](http://lhb5883.spaces.live.com/blog/cns!866B8F96A2761BBE!915.entry)之后，今天我们要研究的就是NI的另一系列低成本PAC——cFP。

首先我们来看看cFP长什么样子：

[![20080509(001)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOSb0abDNb8pNI3SPwH3N7eAq4_7hYkrr2FVyLqLbzxg7V40CE6NoYWTgMCzkUNEqWf4c1gsaRTmrMIpiRqpmLU?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr-UP0UivKkSlrd2jdajakIJhtk8A-D6Ye4rgu0h4AKVZGOGZH7smq0gG_c26bDZ04FcXumZSqtmFQ?PARTNER=WRITER) 

和cRIO一样，cFP也是由控制器、背版、模块（包括模块和端子）构成。

硬件上的准备包括电源、网线，最好再有一个螺丝刀用来跳线。

首先插上网线通电，然后就是软件配置了。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpw0OZpeggdqYl9erKGHwvC0nCeUKhACwxvjDpoX8Q4Qf9rdGeOXebzts-uVqXcfHd8iu6MIxWOerTxqsfHK4Ujz?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzJxUYWMEBcsKRdYoRgNCKw4G4wVUtuCU7puvWWgqHk-QptJKP-NS3GrhYRvuPASl6mycM-OoKsE-pN-RQjR-8e?PARTNER=WRITER) 

打开MAX之后在远程系统按F5，如果RP不错的话就能看见cFP出现在MAX里。

 [![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwxSVu10gwsiZMbj_XAV7yeTjQc708bxbullpntp92wTX2oKlwK6Kddfo8gViTyu-k0wn4bLkNkDRaHoF5pxYX8?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpx80Dm5uPNpDmcdguaZtHvzm5gxshdgsNYQVQRjB4EfmkTzhNDrYKkakUVpZzwNMs50wkt6hHf64uQE7vcKi-JG?PARTNER=WRITER) 

如果看不到可以尝试把reset IP Address跳线拨到On再reset一下，应该就能看到了。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxkG5f3H3CIIm04eMg6bPWaxBP1rzxXdAjq0RhW_yormZNAGExO5zbRyihOeG-guDFU4kIZixJU4qFtWlb21px0?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwtOe_d-ubOuc_2K-VRf9pHHbPfqCa_AT9pQC_HAf5acvkBmSfdqRhnn-mDa4L0W5ZUtzV-pvnyl5NiLKPYBl8-?PARTNER=WRITER) 

然后配置一下网络地址，DCHP比较方便，手动设置灵活一些，看自己的喜好，不过不要忘了把reset Ip关掉。

下一步打开cFP上的安全模式安装软件。

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPPPd2dc6x2NN9SPKPV5Vn-mmq0vGskuah2mgDYkhCk9V3xU4q3XeAxEvIsQ38WeN57RCAIV4xdutKUsuQ70CnH?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMk2hdrIiwwTiqU3tHzOZPYZACoPI1doETg7bEK0Qg5lxo-IJcp9BpybiD03NffgeQiAmM1QzzVJCCB3BCzr12i?PARTNER=WRITER) 

为了能在LabVIEW里面使用cFP，需要安装软件，推荐使用最新的LabVIEW /RT 8.5.1+NI Device Driver 200803，可以直接选择预制好的软件包。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGqCtfuU3kRSBFxxI3XIf25CT70UWNU114Jq7LlvHJSd-mMAPSWPujewbpZI4bld9Y?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzvF-EFc4cH4o90qzOXcQaLpqnQ1HBuj8R_LH8qxl6_qfcT0T6x0R_izZsjnIiQjRkODuPDkSz38PGBb7dntfsb?PARTNER=WRITER) 

为了能使用串口，请确保安装NI Serial和NI-VISA。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpw2FsEKl9Lhsv10_g-rKlFXPGpmEcC52rrvfPL8BEBg1snpDxTRdBkKxK1Yeb18Zt_VoaOzXAK39y80DqzSj0Ku?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr-hj0fIRKSZri29nOUDLVGjA2cU5Mj4eaf1g2-OqaAU01PBQTQhwtHwVg-LME9GZLhRB1cmxZaVnA?PARTNER=WRITER) 

接下来的工作就要在LabVIEW下进行了：

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOap8Ze77jH1E9euKPy1rv2vJOi0RdNxFHKoIYAMb0md0BNAO7CCeOyDcmMGHLMVnhHG7iQVQmV41layraCMLA7?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyC3fw6broyo5Yumwk-KlHYOO0pldwBp-6Fu9qbM1_3vmHEu3iStQgX3k5IMqWLsz3Wldi9Ofau1GyP7qkR-tsR?PARTNER=WRITER) 

新建一个LabVIEW RT工程，基本上一路下一步：

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPi8LN59XdlypKk3xS8xrDlXf2IGRss_CVLVDhJkkE3HOJnmLjgAtKY2DJCgfde_Texfy6AJXybHAUdqWyJ8I_H?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMHfBtG4UzSGZgKR5vTzi2OCl9oC2m4WKgVZcb071oD54I1wZJgIzftYGl9tfBswywE_1n0ImPro_BczYK1ZVAL?PARTNER=WRITER) 

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMIkiDd3OksU1r1dw15aVg7Oiu1G08sTEqjFQyOCJRaiw6iHcUm1-LVn9zpVsBXt3bf612Hh6_7m-x5Acvl4bUH?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOBBETSoUUpiWppAcrNQEj-r-XrwVdSknT-PIH03FO72gMjxsRDaEwVly3V8nWC2r_vY31NEe1ruPUh24iaojK7?PARTNER=WRITER) 

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOmq1lvDfOE7McWEt9INRUINrE4_WgArmMtpT-T1l4TsjeS9v_w1E0FvDbn4upZrSbvC01cJzqcvoOoljbB-H30?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPSSiFxrqXY_9oXQYt1bfllQPklyM4ngiuUq5fb_gZC_qtrlyuWoZ-gbcBzdEPcUBPONkb-7X-BSyrN2FjZAVUd?PARTNER=WRITER) 

这里要选择一下target

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzNuVde38_DDJylnHKRu2G0wVTaFtGkKcuGfnKx4Uh5iSrKaWu5Fuz9Uwjg-B95QxSkI-M_JALnYVIIUoiOGTi2?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxdqZksBh7Glj5nZrJXiG76ZNurqiek4tT61LlVMe9bEmKny6WNW2MLVcXY6yyGqNfd0zO4IBZZhWOhExg4lutA?PARTNER=WRITER) 

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOQFTdKCS7kcwRlCfhemgmuTfClI-fRMCKs2mb96-Cez2hBgl_eB4Jb7TxsljufTca6UsEMFiojoCYAjLISDwGz?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhM3TFr5XfGy0bkxuVFUmgIPOPNGiiayrw-0HKc5_yZtKMW14Y385W4Uh_AoP0JVvr-OEH-JmAWc7srkEVnMtS8r?PARTNER=WRITER) 

然后LabVIEW会自动替你把cFP的资源都添加进去，还替你生成了基本的程序架构。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpykcTHbXyb6mJq87Q3TEY3g0C4eyn-hDfspENf8KnCV2AaShAf23UswT54Sh3Qn_e9b7egHc5Pdx5Kye6rmXTow?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzsaWtt2INALrq3CE2oXcUMtVeF2NSbCZkh04qEuEG9qQ4jSK5R7TfjYqiBErf42_aYn6J1ZwJuPzWSKrRR6FtM?PARTNER=WRITER) 

下面我们就看看如何使用cFP的串口，比较诡异的是你虽然在MAX和LabVIEW工程里面都看不见串口，不过你确实可以使用它（囧rz）

这个是NI网站上的资料：
 <table width="0.000000%" align="center" bgcolor="#eff7ff" border="1"> <tbody> <tr> <td bgcolor="#658abc"><font color="#ffffff"></font></td> <td bgcolor="#658abc"><font color="#ffffff">FP-2000, FP-2010, FP-2015, cFP-2000</font></td> <td bgcolor="#658abc"><font color="#ffffff">cFP-2010</font></td> <td bgcolor="#658abc"><font color="#ffffff">cFP-2020</font></td> <td bgcolor="#658abc"><font color="#ffffff">cFP-2020</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Port Type</font></td> <td bgcolor="#eff7ff"><font color="#0">COM1 (RS-232, DTE)</font></td> <td bgcolor="#eff7ff"><font color="#0">COM1 &amp; COM2 (RS-232, DTE)</font></td> <td bgcolor="#eff7ff"><font color="#0">COM1, COM2, &amp; COM3 (RS-232, DTE)</font></td> <td bgcolor="#eff7ff"><font color="#0">COM4 (RS-485, DTE)</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Baud Rate</font></td> <td bgcolor="#eff7ff"><font color="#0">110 to 115200 bps</font></td> <td bgcolor="#eff7ff"><font color="#0">110 to 115200 bps</font></td> <td bgcolor="#eff7ff"><font color="#0">110 to 115200 bps</font></td> <td bgcolor="#eff7ff"><font color="#0">110 to 115200 bps</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Data Bits</font></td> <td bgcolor="#eff7ff"><font color="#0">5, 6, 7, 8</font></td> <td bgcolor="#eff7ff"><font color="#0">5, 6, 7, 8</font></td> <td bgcolor="#eff7ff"><font color="#0">5, 6, 7, 8</font></td> <td bgcolor="#eff7ff"><font color="#0">5, 6, 7, 8</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Stop Bits</font></td> <td bgcolor="#eff7ff"><font color="#0">1, 1.5, 2</font></td> <td bgcolor="#eff7ff"><font color="#0">1, 1.5, 2</font></td> <td bgcolor="#eff7ff"><font color="#0">1, 1.5, 2</font></td> <td bgcolor="#eff7ff"><font color="#0">1, 1.5, 2</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Parity</font></td> <td bgcolor="#eff7ff"><font color="#0">Odd, Even, Mark, Space</font></td> <td bgcolor="#eff7ff"><font color="#0">Odd, Even, Mark, Space</font></td> <td bgcolor="#eff7ff"><font color="#0">Odd, Even, Mark, Space</font></td> <td bgcolor="#eff7ff"><font color="#0">Odd, Even, Mark, Space</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Flow Control</font></td> <td bgcolor="#eff7ff"><font color="#0">RTS/CTS, XON/XOFF, DTR/DSR</font></td> <td bgcolor="#eff7ff"><font color="#0">RTS/CTS, XON/XOFF, DTR/DSR</font></td> <td bgcolor="#eff7ff"><font color="#0">RTS/CTS, XON/XOFF, DTR/DSR</font></td> <td bgcolor="#eff7ff"><font color="#0">XON/XOFF</font></td></tr> <tr> <td bgcolor="#eff7ff"><font color="#0">Wire mode</font></td> <td bgcolor="#eff7ff"><font color="#0">2-wire</font></td> <td bgcolor="#eff7ff"><font color="#0">2-wire</font></td> <td bgcolor="#eff7ff"><font color="#0">2-wire</font></td> <td bgcolor="#eff7ff"><font color="#0">4-wire</font></td></tr></tbody></table> 

我这里用的是2120，参数就按下图来配置的

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyYmV9_oR25YpfHNrcN-3SZdbLi1RQAr5YH_DvzUx2xS7aT0dj5gKuw0Aguz7f5dD9PsN0pcGxc6JOXMOz8WVXZ?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzeeKvO1yETG9iHfsE3hGfdaLP6cGDXv9XKPWecIdoxOQmZUc8SFshImpKYvmbt5GmL1BUnPEdmYbeamvcehPBZ?PARTNER=WRITER) 

接收端使用Windows自带的超级终端，注意串口属性要和cFP这端匹配

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpx51Q4SAOVXAj6mEDsBehKOViF4UEYhznITPi3pMh87sfwpg9bygsX8WQTJbwotEQpldsx-IIFfQaE8zR54ZRgH?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpx-fLK3qkMe2RaNg5tUgBZ7p0FDxsHI-Ft44aYXVa6_0Kr_g8xxco4noz9gUNJetu22VoUvMDv7YK_foEjTS26t?PARTNER=WRITER) 

程序在cFP上运行以后就会出现这样的结果：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzL1J0a53b63VSmHbMaH-AVhiIRrivOfMUoGkTR9fcEQfhDsLwy3LRDyHCRiFP9idj42cT7YB8yKkcognF4LaR9?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwL0XT21yqKt0bBzfhA6Wlycv8cT3b8AZz9PzN2ZvLCTTisLrcchpaomrIcs5DH1Bck9BQUmopVZrQ-SiNhTZQs?PARTNER=WRITER) 

当然读取也是一样的

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyx5SqHJzftF66J6S1GWHI047zZ0VrqWKYlJxpLC85Ie_F-5pUyPCw56I0PXWik7DSpgQs2lriyyDHbhnI1rwQT?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwiwug-WPRSSWDRuT2L1oU3jud4V2fWusRTVOpB0PIfYyeIZMG6puPWc4EYf3EEqsVk8tpAcUssSPCesXjkX-Rp?PARTNER=WRITER) 

在超级终端输入后就可以读回来，不过要注意的是超级终端是看不到自己输入的字符的。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxYg-WLK5VtAzWNcqLeAM0Wyj45tlBkLkKz3sHYHAr6UzTDobMtaBTGvalMKS5CFV3WFmSCdjMpKNtWHtF6kRzY?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzn6A3vp7uIGRX1QaTv07ElYi1w02ZRBQMXCZ4j21o-YZb5vapeYK67ghu2oSB0HjURGqOHuoQpIA7v-Nq7hvwe?PARTNER=WRITER)
</div>