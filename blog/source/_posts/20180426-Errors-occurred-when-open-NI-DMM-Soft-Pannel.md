---
title: Errors occurred when open NI DMM Soft Pannel
date: 2018-04-26 16:33:39
tags:

---

# NI-DMM 软面板出错的解决办法

安装完NI-DMM之后有时打开软面板会提示

ERROR:One or more elements of the application could not be found.  Please re-install ni-DMM installer again to fix this problem

![NI-DMM Soft Front Panel ERROR: One or more elements of the applicaton could not be found. Please run the NI-DMM installer again to fix this problem ](.\20180426-Errors-occurred-when-open-NI-DMM-Soft-Pannel\clip_image001.png)



这个可能有以下几种常见原因 

## 第一:NI软件安装时没有使用默认目录,测试至少NI-DMM 16.0存在此问题.

 

## 第二:NI-DMM 17.5存在Bug,随机性的打不开软面板,重启后偶尔正常.

 

## 第三:DAQmx组件错乱,之前遇到过类似的报错,NI论坛上也是这种错误.

NI-DMM依赖对应版本的DAQmx,比如是安装了低版本ELVISmx导致DAQmx组件版本不匹配,

解决办法是在添加删除程序里选择添加删除NI软件,把低版本的DAQmx组件删除即可.

<https://forums.ni.com/t5/PXI/DMM-SFT-returns-error-message-says-to-re-install/td-p/470375>

或者最彻底的办法是到 控制面板-添加删除程序-NI软件-删除所有组件.然后安装NI-DMM及内部包含的DAQmx,或者安装NI DeviceDriver Set里面的成套驱动.
