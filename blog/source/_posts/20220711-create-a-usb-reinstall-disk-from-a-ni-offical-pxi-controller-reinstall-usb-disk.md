---
title: >-
  20220711-create-a-usb-reinstall-disk-from-a-ni-offical-pxi-controller-reinstall-usb-disk
date: 2022-07-11 20:12:18
tags:
---

# NI Windows 10 系统恢复优盘复制

## 前言
NI PXIe-8861控制器出场安装的是Windows 10 IOT Enterprise 1809 SAC(The Semi-Annual Channel)版本,会自动更新到次新版本的Win10，对应的是企业版的Current Business Branch.
必须使用U盘进行安装才能识别为正版系统，IOT版本的特殊之处是不连接公网是不需要激活的，有一个延迟激活状态（Windows 10 IoT offers a third option, allowing devices not connected to the Internet to remain in a deferred activation state）而普通的企业版系统是必须要180天激活一次的。

## 注意点：
预装的Windows 10 IOT Enterprise 1809并非是LTSC版本而是SAC，是有商店和预装程序的，也会滚动升级；
官方的优盘虽然是16G的插进电脑是识别成一个8G的空优盘和8G的光盘镜像,使用UltraISO抓取镜像只有2.7G，无法完整抓取,经过刻盘测试无法正常安装系统。
使用复制的方法提取出来的安装包大概有8G,直接复制到优盘时会报错，经测试UEFI启动必须是FAT32分区，镜像的WIM文件有4.5GB，超过了上限。而使用exFAT分区得U盘是无法在NI控制器上正常启动的（按照标准UEFI启动只支持Fat32分区启动，有些第三方主板做了特殊处理支持其他格式的分区如NTFS或者exFAT启动到UEFI）.
解决的办法是利用DISM命令或者第三方工具将Install.wim拆分为一系列Install.swm文件，使用工具拆分WIM镜像后要注意修改应答XML文件中的对应路径。第三方拆分工具gimagex可以图形化的拆分镜像文件。
## 其他
和之前尝试过的利用Acronis True Image提取一键恢复备份文件的方法相比，这种方式安装的Windows可以确保和硬件无关，不会因为网卡Mac地址不同而触发延迟激活失效。
