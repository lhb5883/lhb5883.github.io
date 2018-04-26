---
title: Certified LabVIEW Developer 认证小结
id: 22
categories:
  - 计算机与 Internet
date: 2009-08-31 03:30:36
tags:
---

<div id="msgcns!866B8F96A2761BBE!1370" class="bvMsg"> 

LabVIEW中级认证考试的主要目的就是考察受试者的LabVIEW编程水平,程序风格,文档注释三个方面.详细可以查看下面的文档  

[ftp://ftp.ni.com/pub/devzone/tut/cld_exam_preparation_guide.pdf](ftp://ftp.ni.com/pub/devzone/tut/cld_exam_preparation_guide.pdf "ftp://ftp.ni.com/pub/devzone/tut/cld_exam_preparation_guide.pdf")

下面这个链接已经列举了一些注意事项,我再补充几条:

[http://cygnus-wei.spaces.live.com/blog/cns!CD5F4D351CB23EC!1406.entry](http://cygnus-wei.spaces.live.com/blog/cns!CD5F4D351CB23EC!1406.entry "http://cygnus-wei.spaces.live.com/blog/cns!CD5F4D351CB23EC!1406.entry")

1\. 善于利用LabVIEW自带的模板和VI,例如定时迅捷VI,读写电子表格文件VI,状态机模板,子VI模板几个都要熟练掌握.

2\. 最好使用LabVIEW英文版开发环境.这样无论是模板还是控件名字都是默认英文,可以减小工作量.

3\. 不要忘记在状态机模板里加上错误处理.

4\. 写完程序一定要留调试和注释的时间.

5\. 尽量将状态机Case结构里的代码封装为子VI.

6\. 能用TypeDefine控件的尽量都用TypeDefine控件,方便程序维护.

7\. 不需要用户交互的前面板控件最好隐藏掉.

细节: 

1\. 框图和前面板大小:根据考试要求最好限定为1024x768,要扩展尽量水平扩展.现在显示器以宽屏居多,方便观察整个程序.

2\. LabVIEW配置,如果你到手的机器配置修改太多,例如字体等要改回来很麻烦.最简单的办法就是删除LabVIEW的INI文件.然后在工具-&gt;属性里取消前面板控件:显示为图标.

3\. 状态机里面的等待函数一定要修改,设置为1是个不错的选择.

4\. 使用Ctrl+鼠标拖拽扩展程序框图时一定要慎重,避免程序连线错位.
  </div>