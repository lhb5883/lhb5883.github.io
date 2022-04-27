---
title: 20220402-labview-2021sp1-released
date: 2022-04-02 10:37:43
tags:
---
# LabVIEW 2021 SP1发布

NI刚刚发布了LabVIEW 2021 SP1和鸽掉的Linux RT驱动支持,可以说现在才是LabVIEW 2021的完全体，以下就是NI平台安装包2021秋季版的下载地址，推荐使用LabVIEW RT的开发者进行安装：

Software Platform Bundle Fall 2021 32位英文版
Name	Checksum	File Size
Fall 2021	(MD5) 7d6427bbdb3460aab7958e4a4a6778c6	48.23 GB
	(SHA256) bbd3ec07ff10eb9fec2e9420e6d9b643ee4d7eea4d3481cf1e3797e2a4f444bc

From <https://www.ni.com/en-us/support/downloads/software-products/download.software-platform-bundle.html#> 

Software Platform Bundle Fall 2021 64位英文版
Name	Checksum	File Size
Fall 2021	(MD5) 7c7a61f00e68436a7617913077f3dea6	59.85 GB
	(SHA256) 88f4eff780d9c2ecd3d8791a410aa652b4602ed27c5cbcbd09bb54e70f62f66e

From <https://www.ni.com/en-us/support/downloads/software-products/download.software-platform-bundle.html#443873> 

Software Platform Bundle Fall 2021 32位中文版
Name	Checksum	File Size
Fall 2021	(MD5) d52563b081ece419311ec56446cec29a	48.46 GB
	(SHA256) 943d68ccefbdfa9aa951a809de2685bffa54bb5b5d7430fb4fdd75a35536a7fe

From <https://www.ni.com/en-us/support/downloads/software-products/download.software-platform-bundle.html#443869> 

下载地址
https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle-x86/21.5/offline/ni-software-platform-bundle-x86_21.5.0.49279-0+f127_offline.iso
https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle/21.5/offline/ni-software-platform-bundle_21.5.0.49279-0+f127_offline.iso
https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle-x86-zh-cn/21.5/offline/ni-software-platform-bundle-x86-zh-cn_21.5.0.49279-0+f127_offline.iso

LinuxRT离线支持
这个类似于NI之前支持Parlap ETS RT的控制器Target CD,需要有这个才能在下位机RT安装软件。虽然不知道大包里面是否已经包含（2021春季版没有包含，2020的春秋两版大包里面包含了，2019的大包里面不包含，属于薛定谔的包含态），因此LinuxRT离线支持下载还是推荐下载：
NI Linux Real-Time Offline Installation Support 21.5
Name	Checksum	File Size
21.5.0	(MD5) 4bffcbe21bc0b766accfb6b364c37f66	4.59 GB
	(SHA256) 1e73e7bffbb22e9b09866d6b941332da53a37f44413b827d57ef4008b7dd2be9

From <https://www.ni.com/en-us/support/downloads/software-products/download.ni-linux-real-time-offline-installation-support.html#> 

https://download.ni.com/support/nipkg/products/ni-l/ni-linux-rt-offline-installation-support-21.5/21.5/offline/ni-linux-rt-offline-installation-support-21.5_21.5.0_offline.iso

此外这次更新，LabVIEW 64bit也有了Realtime 模块，加上之前32bit工具包的淘汰，这样在官方层面，LabVIEW 64bit的模块和工具包就和32bit完全相同了。

Veristand现在也更新了2021版，并且是64bit架构，只支持Windows和Linux RT 64bit，完成了系统64bit化迁移。自LabVIEW 8.5抛弃了在Windows内核打补丁增加实时性的RTX之后，IntervalZero同厂的在DOS上增加Win32API的ETS也遭到了抛弃，业界在主流系统上改造为实时系统的共识就是LinuxRT，维护一个实时系统的生态需要的投资过于庞大，只有开源的Linux才能确保长期的演进。

如果使用Veristand2021推荐把下面的Eclipse和RT镜像装上。



以上的下载链接如果下载失败或者速度过低，可以加入迅雷云盘里面的云下载，然后从迅雷云盘中下载，速度相对稳定一些。
