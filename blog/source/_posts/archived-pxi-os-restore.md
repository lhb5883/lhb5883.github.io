---
title: PXI控制器系统备份软件选择
id: 19
categories:
  - Computers and Internet
date: 2009-11-24 07:52:30
tags:
---

<div id="msgcns!866B8F96A2761BBE!1389" class="bvMsg">

虽然NI的控制器质量非常稳定可靠，不过如果使用Windows而非RealTimeOS的话，系统备份恢复软件就是一个值得考虑的问题了。

为了找到一个好用的恢复软件给我们的8176上个保险，来来回回测试了多种备份软件。

系统备份与恢复软件厂商目前主要是Symantic赛门铁克和Acronis两大厂商。其中Symantic以GHOST系列强大的功能闻名，在收购了PowerQuest之后其实力不可小视。Acronis以True Image系列软件的方便易用与稳定可靠被NI作为系统默认的硬盘恢复方案。

我初步的目标是找到一个能在Windows7下备份和恢复整个分区的软件，取代我一直使用的DriveImage。不过该方法需要拆开控制器，所以要是能做成多启动这种方案也不错。

下表是一个简单的比较
 <table border="0" cellspacing="0" cellpadding="0"> <tbody> <tr> <td width="165">控制器型号</td> <td width="174">Norton Save&amp;Restore/
Symantec Backup Exec System</td> <td width="107">双启动GHOST</td> <td width="138">光盘/U盘版GHOST</td> <td width="198"> 

Acronis True Image OEM
</td> <td width="206">Acronis True Image 2010</td> <td width="246">Power Quest Drive Image 2002</td></tr> <tr> <td width="165">PXI-817X/818X（Intel8系列芯片组）</td> <td width="174">OK</td> <td width="107">OK</td> <td width="138">Fail</td> <td width="198">OK</td> <td width="206">不支持Windows2000</td> <td width="246">OK</td></tr> <tr> <td width="165">PXI-819X/810X/8130（Intel9系列芯片组/Nvidia N-Force）</td> <td width="174">OK</td> <td width="107">OK</td> <td width="138">OK</td> <td width="198">OK</td> <td width="206">OK</td> <td width="246">OK</td></tr> <tr> <td width="165">PXI-8108/8110（IntelG系列芯片组）</td> <td width="174">OK</td> <td width="107">未知</td> <td width="138">Fail</td> <td width="198">OK</td> <td width="206">OK</td> <td width="246">OK</td></tr> <tr> <td width="165">功能</td> <td width="174"> </td> <td width="107"> </td> <td width="138"> </td> <td width="198"> </td> <td width="206"> </td> <td width="246"> </td></tr> <tr> <td width="165">在Windows下备份和恢复分区（用于在PC机上恢复系统，适用于硬盘数据完全丢失无法启动等情况）</td> <td width="174">只能用于系统盘</td> <td width="107">/</td> <td width="138">/</td> <td width="198">OK</td> <td width="206">OK</td> <td width="246">OK</td></tr> <tr> <td width="165">在非windows下备份和恢复分区</td> <td width="174">无</td> <td width="107">OK</td> <td width="138">不适用老控制器</td> <td width="198">OK</td> <td width="206">OK</td> <td width="246">无</td></tr> <tr> <td width="165">操作系统支持</td> <td width="174">XP/VISTA</td> <td width="107">/</td> <td width="138">/</td> <td width="198">2000/XP</td> <td width="206">XP/VISTA/Windows7</td> <td width="246">2000/XP</td></tr></tbody></table> 

目前GHOST的二次封装而成的USB GHOST，光盘GHOST、一键GHOST等等版本极多，不过能兼容NI大部分控制器的GHOST版本并不多。而企业版GHOST套装使用和配置极其复杂，操作简单的Windows下备份和恢复的软件在系统崩溃后就没有什么用了。所以值得考虑的就是系统恢复光盘里自带的Acronis True Image OEM版，是一个简单可靠的一键恢复系统，不过一旦恢复就会使系统恢复到出厂状态。需自由备份和恢复就需要完整版的软件才行。

不过我们其实需要的功能往往也没有那么复杂，只需要能恢复系统到一个安装调试好所有软件的状态，那么这时候就可以用到下面这个小技巧了 。

1。正常安装Windows，注意不要选择安装F4一键恢复。

2。分区、安装软件、配置程序。。。

3。将系统恢复盘的CDROM:OSPXI_VXI$OEM$$1SYSPREP目录下的ACRONIS.XML，ACRONIS8199_ENABLE.BAT，ACRONISTRUEIMAGE_8199.MSI三个文件复制到c:Sysprep目录下

4。运行c:SysprepACRONIS8199_ENABLE.BAT，重启系统后就会自动备份操作系统，完成之后在系统启动时按F4就可以一键恢复了。
  </div>