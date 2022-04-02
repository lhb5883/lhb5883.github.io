---
title: 20191231-how-to-work-around-some-bugs-in-2019
date: 2019-12-31 18:54:54
tags:
---

2019被bug坑了不少，不过还好找到了一些解决办法

KB2538242反复安装解决办法：手动安装



下载 KB2538242

Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package MFC Security Update

https://www.microsoft.com/en-us/download/details.aspx?id=26347

安装 KB2538242 会提示安装路径错误，估计是打包计算机的默认路径

C:\Users\Ansifa\AppData\Local\Temp\IXP000.TMP\

手动选择到本机对应路径，安装完成后重启。



一句话说明：搜索结果可以用Auto summary字段列出高亮关键字

详细说明：

自Win7以来库功能让索引搜索向大众普及了不少，不过Win10的搜索有一个很大的倒退就是搜索结果摘要从两行变成了一行

变通的办法就是使用详细视图代替摘要视图，然后显示Auto summary字段即可，只要你屏幕足够宽就可以显示的比内容视图要多

另外 Windows 10 1909更新把搜索栏换成了UWP所以经常挂掉，解决的办法就是任务管理器里面重启explorer：

如果是土豪的话，可以购买Agent Ransack或者File Locator Pro作为替代方案，并且可以把搜索结果导出纯文本。

免费版的缺点是无法建立索引，不过文件量不大的情况下也基本上够用了。比Windows索引搜索的好处是对关键字和复合条件搜索支持更好。变通的办法就是先用Windows搜索筛选出来可能有结果的文件，复制到另一个目录，然后再用Agent Ransack lite导出结果。

最后是一个iOS的feature

Spotlight do not appear "Ask Siri"

System Language must same as Siri Language.

系统语言必须和siri语言一致，中文系统配中文siri，英文系统配英文siri才可以，否则是不会出现Ask Siri的。

 

Ref

https://appletoolbox.com/siri-not-working-troubleshooting/#Check_For_Any_Restrictions_on_Siri

https://the8-bit.com/how-to-access-siri-from-spotlight-search-on-the-iphone-and-ipad-in-ios-13/

https://sspai.com/post/56887 

