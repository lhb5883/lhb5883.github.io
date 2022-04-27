---
title: cRIO摧残记（下）——FPGA篇
id: 36
categories:
  - Uncategorized
date: 2008-04-17 02:05:11
tags:
---

<div id="msgcns!866B8F96A2761BBE!915" class="bvMsg">

同志们，在本人的无良拖稿之下大家期待已久的cRIO摧残记终于迎来了下篇，真是可喜可贺啊~撒花庆祝！

在MAX里面的配置请查看[**这里**](http://lhb5883.spaces.live.com/blog/cns!866B8F96A2761BBE!729.entry) 下面我们直接从LabVIEW开始：

首先确认你安装了以下或更新版本软件：

LabVIEW 8.5、LabVIEW RT ETS 8.5、LabVIEW FPGA 8.5、NI RIO 2.4、NI Device Driver 200803，

这是本人所安装的软件：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxCB9abFFHEqcIFTU88U6yCJxBWwCnmAo1TvReAeNmBg03BzeOa5IIfKfg6-uXUTY7mIejCtHefqXY3fR_TILty?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr-Ct8-v8z-CmWeXf7SyzdyG-ZavotkqHoirXTPOOqtAQN37uxSepQZ_-kDc6FGnishMCXjPLhxOsg?PARTNER=WRITER) 

**<font color="#ff0000">建议安装好以后用LabVIEW把安装目录Mass Compile一遍。</font>**

打开LabVIEW 8.5，新建一个FPGA工程：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRH-_AUqc9SPdWGe-QgaNunNuLiIpKyRJSmw-Td88QZgl9N3-xE4ygCJTvV_M0klci4?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuREiz1FKBzCweIH9YjS2WZKCfhG_XGCPrE1HOBNoBMzUR_ZXw4ckWxrm-vtKUMe1XXI?PARTNER=WRITER) 

选择FPGA目标类型：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGtHlA_DIx9isw1gWAj_ekqa094No4O5YFbDdWrGTEK3P4sNUqIX1LPgGdvDToH9p0?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRG4wP-wjQnssJ9hRVU_sa6Rz-LDK9BgswfqkyrH98sHStn5YdhPp_pXEJ4Z52WtcOQ?PARTNER=WRITER) 

确认cRIO已经配置好：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFxZboqLHciW2PBpMaaVKeVhqEhOJ0wPEjBw968-bdlHHr4F8lIUbadVGBsAO-fmNU?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRETomBdMJv4_uDJEW3hxjsLZRtLnqGcQAeIgE3gbDJN9xc_DhaEzu8r-SKIGC0RRqo?PARTNER=WRITER) 

如果一切正常的话应该这样：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRH-hmk5gCuVIjxJFUEUVLqS4_8wyw8EcIBvfo-V-K6WuFGt1U4V6SFspeGXU73QXWQ?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGUJYa6sQ2e7sb2rfJD3CzyUy43m1nCggMnYuH73HfrEHrppj7kmF3ViPn8J__Gjmk?PARTNER=WRITER) 

这里要选discover

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFCX3j3oF4j0XwfpqM6Zrk-2nwscwn7eEFziGj-AW6uSsJrLsTn1q2fl-6TCT2pMNc?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGMWKTc70BqmkgA2mgsXmAWLHW4fbA8RhgAQZKGYNYFPkYrh0OPKyg6NN6B-BAx_3c?PARTNER=WRITER) 

这样就会列出cRIO里面所有的模块：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRF6QCMr52FzDX0roswjJeJyUHnJKxKcnhOr3QAr-d9eD9htxvyoVkPQRjUFCt_rcmw?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFDqwE_neppTZCdHvgTKFaw-zymNjGhxuH7mHVEd4L9pqyJy4tVm0gSREB8T-ZjN0M?PARTNER=WRITER)

这个向导我已经[介绍过了](http://lhb5883.spaces.live.com/blog/cns!866B8F96A2761BBE!729.entry)，这次就取消，咱们自己动手丰衣足食。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFZTq6nX0zwmoa3yyg2pKgowXEkzqT7Jewbr1nZuq4PVmb16XIpxbtLTfSSPdG6fWM?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuREaHdaWfVJgPhqc9omvyUqS-kajBN5TPY2C72pf2pWi2ktuEecMeH5ZGin8eCWiS9w?PARTNER=WRITER) 

我们首先在FPGA上新建一个VI 

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGdDQdQM4YK_kSx_72sZHvztghzS8LjL0z0s5KI9se8XfHTVJJhnDhpAgKce3AZ9vI?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGkzo5MHp0_rFpDNit0x5jaRu1t3723iEDU-3XZfbGj24UhukUJ_j1kjGnK_6ZQF4Y?PARTNER=WRITER) 

我们把要访问的资源都丢进FPGA VI里面，**<font color="#ff0000">并创建相应的控件</font>**。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGbmtIlZgBLjIwIUI2tfSVxuCKHK2VA7a-rkOecT82JXcSKFZpSZjR3G4JoNujAPE0?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGVezOejCc3nZ6CAxEcSECNUpt2pNr_lDv4L0Q9jIEY5K-AGSIUHa8MjJ9tmsElSpw?PARTNER=WRITER) 

然后在cRIO的控制器上也新建一个VI：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGuWExQ6nm0MI52jTgosw84HuF4pp7D_liXHSLZClnXS8mv7u7EubjngBMpNH0SVgU?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGZI9h4KpIIErx8g6h8f-FRsCpPvo7E1o0JmkREtpowNKWKuFnGkhgVqgqwInY155I?PARTNER=WRITER) 

先扔一个FPGA引用：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFzB8LjhhGyLvIVW5j4Hskm-3oQVy-tQ_NWpT-BhoQ_EeEVInyk8vzQWkzcnqcmzoU?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRETjIqCuC12TxdiwXuUHuCOcxYOFLJ9NQJixgy-_LCrf-mt9O58FRf7lVt4iloHQm0?PARTNER=WRITER) 

然后选择VI：

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRF8l6CWbvpNOAbZjHLFYoulqrt3AU9J_tYpyPgI39qE9qf432ZbJgD0XMv8x3ZfsFs?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRHvvNu5shuH212Ofp_MlIcLkmQ0e-7tLUomXd8oPhsmPPTnQPIIwS_wwS4O0pmEHyE?PARTNER=WRITER) 

中间通过[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRES8ONRhfvf77L00y0fGGyx6-STzuWGJoXP1wQ_Q-54ueaHmNSLLO60APp28b3FmkM?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFAuv0rCGxZ-tSk3BLs5BvUJwEugmvZVgwIH8np3j_367663T3YQgJWRtCXabT6ojc?PARTNER=WRITER) 对FPGA进行操作：

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMVE12aNFzOEzVg4jZZxSb-vOnenBQXy5AgreIKy-9aGNqw1zc6FUJd7H5fu-zWy6_d5HNdZLDzuDjsdYTC2aHS?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr_kofxOb-g3lFoPYLyPxsxPI7dnG70qAGhn3IwpL4Qo9J22ibqtTUUSqWJ3wFvuJFbMyvuUonbb2A?PARTNER=WRITER) 

最后不要忘记关闭FPGA引用。

这样一个最简单的FPGA程序就写好了。

我们这时候还不能直接运行程序，因为FPGA还没有编译：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxkmJiPQLyVfjIE8wImomdru1G2FrdlW10aD9kqI_2M3TlNsm38o30BB_z4r81O_gFtUqvEskaqDnzoYyiryVdC?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzwzE7ajkkJ305_XfLqPk9Wh5p9weFZR11-6RRbX8wTfFcKq4m4jrmpYywK5CBO8_C3zeu1Xo6o0J35i8l-1nQ3?PARTNER=WRITER)

我们在FPGA VI上右键选择编译：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyfSJ-COJfS_-G9K0Owh3k5oVIpckTJu2ZgQLOFJsV8mIdvAFNDcX5dlu3sE8uWw9L6kPMbkbq8r66nFizbLjt2?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzm40xhVzMGQFb2OHjp84ns-LVoMPvr7V1vOVhbJClwXeBHrSvZLB6pXxS1413m70wuO0OWNzyolQWC4i6aYvPV?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzyQaYSiuKeAf-i1DQW1h0mOhgplK7PqhhVoAhHSksze0JGxGcJ7S62qMFllGRO0OrXnly8_UzIfNfr9r4tOMeJ?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyYEj5k8C9nI5EFsZVLYspVThWcmE_6yNHmM0tLoe9bPu8A7_9qpz6uYFYYOMPnpfRRQ_mMC7ekioSYLD4ou68r?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxyalXakskdWjoWmg4b6rYpMT4BDsr_yvhELxkazAc5rZeDG84fMOzDZYvq5u-AJEKs0ND8oGzz2XB0802MS6w_?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOmL63LlJgQyqIBZLVVCdEQB4IpOLu58jd8lVYwWbUNRgu9eQ5A2rFQsDKres5PuH5WDeB0PcnG5_4lQk8DRNT1?PARTNER=WRITER) 

漫长的等待之后我们就可以运行我们的FPGA程序了：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyxdSdziVPpFUwUDm6khOwmrdDyg9AyyfKLZwdpvZZLDewkxmm3nvBsdajWUsyJu7IgowfiwTameGj0n1rfMHKb?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpylNMNt2Bd1k2V7W3avS2ZEP8QhT4w8_WtkDTitIvFt3XLDI69JDQfkKUCJaCHsdsWPpXhNTjlgMbZ2KyYAPb6j?PARTNER=WRITER) 

要注意的是**<font color="#ff0000">直接运cRIO上的程序</font>**即可，无需运行FPGA程序，因为cRIO会通过[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFzB8LjhhGyLvIVW5j4Hskm-3oQVy-tQ_NWpT-BhoQ_EeEVInyk8vzQWkzcnqcmzoU?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRETjIqCuC12TxdiwXuUHuCOcxYOFLJ9NQJixgy-_LCrf-mt9O58FRf7lVt4iloHQm0?PARTNER=WRITER) 自动调用FPGA程序。

最后是友情提醒+小小广告：

此程序仅仅是为了测试cRIO能否正常工作，如果要进一步发挥出cRIO的强大潜能，

请联系[泛华测控](http://www.pansino.con.cn)、[NI中国](http://www.ni.com/china)了解更多详情和专业培训课程。
</div>