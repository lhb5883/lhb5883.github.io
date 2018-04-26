---
title: '[Code Share]如何用LabVIEW取得计算机主频'
tags:
  - .NET
  - CPU Ferquency
  - LabVIEW 2009
  - LabVIEW 2010
  - Win32API
  - WMI
id: 249
categories:
  - LabVIEW
date: 2010-10-14 11:23:06
---

大部分Windows下程序都是使用计算机计时器计算CPU主频，（当然也可以跑个算法自己算）最基础的就是这个了：

*   **使用Win32API取频率**  

好处是功能简单速度快，下面代码没做返回值处理，如果计算机没有高精度计数器（这个可能性比较小）有可能出不来频率，详细可以去看MSDN：

![WINAPI QueryPerformanceFrequency](http://lhb5883.files.wordpress.com/2010/10/winapi-queryperformancefrequency.png "WINAPI QueryPerformanceFrequency")

*   **.NET&#160; 利用WMI获取系统信息**  

这个接口是使用系统信息（C:\Windows\System32\msinfo32.exe）能拿到的信息更多，不过方法复杂，速度也慢。

&#160;

![System.Management.ManagementObjectSearcher](http://lhb5883.files.wordpress.com/2010/10/system-management-managementobjectsearcher.png "System.Management.ManagementObjectSearcher")

这两个算法都在Win7 32bit，LabVIEW2009SP1下测试通过。