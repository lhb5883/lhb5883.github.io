---
title: 给7Zip压缩自动增加时间戳
id: 268
categories:
  - 计算机与 Internet
date: 2013-09-29 16:32:29
tags:
---

WinRAR压缩文件有一个很方便的选项是在文件名追加压缩时间,但是RAR是收费软件,价格不菲.使用7-Zip就没有这样的功能了么?

其实只要自己动手也能丰衣足食,给7-Zip加上这个功能:

首先在运行中输入

1.  <div style="background:#f4f4f4;"><span style="font-size:9pt;"><span style="color:maroon;">shell</span>:<span style="color:maroon;">sendto</span>
				</span></div>

打开自己的发送到文件夹.

在文件夹新建一个文本文档,并贴入以下代码保存为ANSI编码

1.  <div style="background:#f4f4f4;">[<span style="font-size:9pt;">set</span>](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=set&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99)<span style="font-size:9pt;"> hh=%[time](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=time&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~0,2%
</span></div>
2.  <div style="background:#f4f4f4;">[<span style="font-size:9pt;">if</span>](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=if&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99)<span style="font-size:9pt;"> %hh% LSS 10 ([set](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=set&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99) hh=0%[time](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=time&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~1,1%)
</span></div>
3.  <div style="background:#f4f4f4;">[<span style="font-size:9pt;">set</span>](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=set&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99)<span style="font-size:9pt;"> dst=%[date](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=date&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~0,4%%[date](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=date&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~5,2%%[date](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=date&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~8,2%_%hh%%[time](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=time&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~3,2%%[time](http://search.microsoft.com/default.asp?so=RECCNT&amp;siteid=us%2Fdev&amp;p=1&amp;nq=NEW&amp;qu=time&amp;IntlSearch=&amp;boolean=PHRASE&amp;ig=01&amp;i=09&amp;i=99):~6,2%
</span></div>
4.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">"<span style="color:darkred;">C:\Program Files\7-Zip\7z.exe</span>" a %1_%dst%.zip %1
</span></div>

修改文件名为

7zBackup.bat

使用时选中需要压缩的文件或者目录,选择发送到7zBackup.bat即可。

以上在Window 7 64bit，7-Zip 9.2 64bit下验证通过。