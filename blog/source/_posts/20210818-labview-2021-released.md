---
title: 20210818-labview-2021-released
date: 2022-04-02 10:38:50
tags:
---
# LabVIEW 2021 Released

经过上周末的NI网站维护，LabVIEW 2021终于发布。

从这个版本起,LabVIEW不再支持Win7,Win8等老操作系统,最低也要是Win 10起,以下是支持的操作系统:

Windows 10

Windows Server 2019

Windows Server 2016

除此之外虽然LabVIEW还有32bit版本,但是已经不再支持32bit的OS了，也就是说只能在Win 10 64bit上安装和使用。

对于今年发布Win11，NI还没有作正式声明是否支持，不过理论上来说是可以靠向下兼容支持的，但是如果微软在权限上继续收紧，也许会有未知的bug。

对于LabVIEW RT 从这个版本正式去掉了Pharlap ETS支持,也就是只支持Linux RT一个系统了,不过要注意的地方是NI的硬件板卡对Linux的支持和对NI Linux RT是有区别的:

Linux支持的板卡较多但可能仅有板卡驱动和C接口，没有LabVIEW接口；

NI Linux RT支持的板卡较少，目前NI还在不断地移植，除了板卡驱动，还有LabVIEW支持，能够直接用LabVIEW调用板卡。

例如之前NI Switch一直说在20.5加上NI Linux RT支持，但是NI一直没有发布20.5，网站上能下载到的就是20.0。

此外之前LabVIEW NXG Web Module现在变成了独立软件“G​网络​开发​软件”，不再依赖NXG