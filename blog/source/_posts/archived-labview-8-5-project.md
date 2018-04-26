---
title: LabVIEW 8.5工程管理器-冲突解决
id: 45
categories:
  - Uncategorized
date: 2008-01-31 01:06:37
tags:
---

<div id="msgcns!866B8F96A2761BBE!485" class="bvMsg">

自从LabVIEW 8.0新添加了工程管理器之后，给我们带来了很多方便，不过讨厌的冲突问题也随之升级。。。。。。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRHNd9xywfwKM4ZgykNF-0fxL9Bg3UNaeYL31r66MX16riltc3q3Cjenrb5wy1kP1DI?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGcSGi2Ujk4uPcJlzpekFE7gQp0FOKoh-FeHhScWgcpmYCaodb0gR1fdR76v9ziYBg?PARTNER=WRITER) 

在LabVIEW 7里面，当我们打开名字一样的VI时就会弹出来这样一个对话框，告诉我们名不正则言不顺，名字一样的只能有一个，不是你死就是我活。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRHQJ2MixiygKbZkiQ2SYMwwAq59l3AvEu9S4OjowUnOSGfyRX2DucDkEvvWVX1aEAA?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuREPkk0XmQBViLIU-YodFxX1a_sua6RUADbvXF85RusYalvPPC0cL3ufolpu1cigbJ4?PARTNER=WRITER) 

而在LabVIEW 8里面就更加变本加厉，只要在一个工程里，还没有打开就告诉你：有问题，未解决。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFEHR74rec3Fmn8u8U2hpbCa-yaZ7aWKNGiDVoYE3qSxaf8KqoHeWDQ9JtCKer_0O8?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGALeHNeQrA4QvX5d7b584XAQ6pZq5ktFGpI5oI8Z7P9oBxrHRxMnO-meHYjbpoteQ?PARTNER=WRITER) 

一般来说这种小CASE只要说服教育，将其转化为LIbrary即可解决。

然后就是老同志遇上新问题：如何在8.5的自动更新文件夹里移动VI的位置？

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGMj3vZPXrae4aJ6bb5rga4y99gwxkr7ucqtInZwTS7po0vRz4Ai3fM1a9mjN_CVJc?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFAR6eeNDtUY28rc-gfsu6VOd4QwdUKCX-F24pvcZRbhravzhD8ia7PBZTijZoHzqo?PARTNER=WRITER) 

这个自动更新文件夹啊好是好，但是就是太讲原则，文件夹里有什么他就有什么，想拖到新位置---NO WAY。

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFmqanLzlwZ5Hu01VeGly0SQzYfxCkFsBR1SjAHV-RYxpUNe05J5igwMemNFaZM3dA?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRHeEOisrcnSX7Ki9wV_4s1y8muejx2RQEEsP95bA6UZPLwHk75-qupjevLo16eyFts?PARTNER=WRITER) 

可能你要说，直接在Windows资源管理器拖动之不就ok

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRG2ap5vPy23jHXFCuFCgQEdzvTdr5nI04UetvkK7u4vKk6J0ERpVKJUFwxDAsDT0Is?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGfY7xpQBGuVFapAwxQ5r_6Vy_8OwE6pT46KmNMPS7YMWGB1TKrSEagFma_FXO0BGo?PARTNER=WRITER) 

en ?这个是啥？

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRFbkpOXxp5UND8SBWbk2lBtE_QbBT7MtVbVEX-KHn5UbSxz551GAqkseuzPevtdlyA?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRG4F1ETPyrDNfANHgcL_Sywd9MZ2ubIL4sVSq6temPWg0OdOvmtLGlpuDsV_tcyZK0?PARTNER=WRITER) 

还好只有一个，

[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRF5tEm9TFeNog_GSXXgMjKndh7Pnb1Xubmr1XlY3PdYWLo5MKqU72zTQznQGFNnapo?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRF6juxSBZglk44aD36rQxR9v1sRiYs7BVRfNns30r2xmptTAeDwn7DoN1uBlfnN-R0?PARTNER=WRITER) 

不过还是不爽，怎么才能没有冲突呢？

当当当当，正确答案即将揭晓，请大家鼓掌。

[![image](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr8PeP6dggYNW7rl5tpP5t6RCGRzJxExGHiWWmZJneYFGXIAlqlhLYj8RTf4QQc1G6BhabWGjXtQQQ?PARTNER=WRITER)](http://byfiles.storage.msn.com/y1pf3H7KtzkuRG3sNeTRK__JA5AmAQEu5mdBZdU8jLKkbQhA4Wj9Vp8uRSnYDjZLU8q56-hfXxytOw?PARTNER=WRITER) 

正确答案就是在FILES里面拖动，从此轻松无忧。

[![image](http://by1.storage.msn.com/y1p8NjIsGi7lpxD-uFHfpgCYKETdX_gzjTpz1kZ3AgEXO_3ePrCtzEnFwbMnhJtrDzLgsMijzJ62wZvgoTrh56o8lwcLdYG5qH-?PARTNER=WRITER)](http://by1.storage.msn.com/y1p8NjIsGi7lpwoshdi1alynJo9yl_3wMB3PfiOqNu-40zIiPK7GMo1rQHG-kqtch6TBGQieyCnW3C6F1_kWQFxKwLcnNbzjKL6?PARTNER=WRITER) 

LabVIEW会自动处理牵涉到文件。

神州行，我看行。LabVIEW 8.5 今天你升了么？
</div>