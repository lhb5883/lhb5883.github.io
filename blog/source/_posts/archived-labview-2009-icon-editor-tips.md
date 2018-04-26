---
title: 关于LabVIEW 2009图标编辑器技巧两则
id: 9
categories:
  - LabVIEW
date: 2009-12-31 02:08:15
tags:
---

<div id="msgcns!866B8F96A2761BBE!1472" class="bvMsg"> 

LabVIEW2009的图标编辑器在书写字符时会出现模糊的现象

![image](https://aftv2q.bay.livefilestore.com/y1m80sTh9OID-hm_xBpKcQJPf8_l_40wO8nkraFJxyFseIXlBkmBq6Vj0WvgUUJRsb4Hu6IyDvmuyjJ5oSATC62_cykAwMJ_B852vsgnYTj3FYtTjnYLFL_pgHzx0IgBXG85Y_BTw4lQy5CJIHojMzYrg/image[11] 264EED05.png "image") 

这个BUG是Cleartype导致的，Cleartype是一种LCD优化显示技术用来平滑字体，在大屏幕上显示大号字体也不会有明显的锯齿，但是对于小号字体就会有模糊的现象。

IE8中就强制打开了这一技术来获得更好的观感。（说句题外话，虽然我现在主浏览器是Google Chrome，不过对页面渲染效果最好的还是IE8）

如何解决呢？XP在我的电脑上右键，选择属性

![image](http://lhb5883.files.wordpress.com/2009/12/image5b145d.png?w=258 "image") 

在高级标签页选择设置

![image](http://lhb5883.files.wordpress.com/2009/12/image5b25d0e8e803e.png?w=205 "image") 

在视觉效果里关闭平滑字体边缘。

Windows7/Vista在控制面板里搜索ClearType

![image](http://lhb5883.files.wordpress.com/2009/12/image5b55d6f2b8dd0.png?w=300 "image") 

取消打开Cleartype。

![image](http://lhb5883.files.wordpress.com/2009/12/image5b85d6f5a7be9.png?w=300 "image") 

这样打出来的字就不会模糊了。

![image](http://lhb5883.files.wordpress.com/2009/12/image5b175d7d26dedb.png?w=300 "image")

关于Cleartype的一些相关链接。

Wiki的介绍

[http://en.wikipedia.org/wiki/ClearType](http://en.wikipedia.org/wiki/ClearType)

M$自家的介绍

[http://www.microsoft.com/typography/cleartypeInfo.mspx](http://www.microsoft.com/typography/cleartypeInfo.mspx)

XP的Cleartype在线调节工具

[http://www.microsoft.com/typography/cleartype/tuner/step1.aspx](http://www.microsoft.com/typography/cleartype/tuner/step1.aspx)

离线版

[http://www.microsoft.com/typography/ClearTypePowerToy.mspx](http://www.microsoft.com/typography/ClearTypePowerToy.mspx)

另外，关于图标编辑器禁用的办法：

 [http://ruanqizhen.spaces.live.com/blog/cns!5852D4F797C53FB6!4848.entry](http://ruanqizhen.spaces.live.com/blog/cns!5852D4F797C53FB6!4848.entry "http://ruanqizhen.spaces.live.com/blog/cns!5852D4F797C53FB6!4848.entry")

我个人觉得LabVIEW最好的办法是支持标准的图标文件，这样可以更加开放。例如M$的VisualStudio图标编辑器其实就是第三方的Axialis _IconWorksho_p

还需要增加更大分辨率和颜色数的支持，能够在图标里提供更多的信息，像LabVIEW Lego开发软件的图标就很有特点。当然这个工作量就非常巨大了，需要修改大量的图标。
  </div>