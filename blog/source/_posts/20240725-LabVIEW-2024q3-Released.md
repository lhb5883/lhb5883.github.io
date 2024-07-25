---
title: 20240725-LabVIEW-2024q3-Released
date: 2024-07-25 21:29:59
tags:
---



LabVIEW 2024Q1发布的时候我连博客都没写，因为基本上没什么更新，不过这次的Q3更新还是要稍微提一下
一个是对Dot NET 8.0的试验性适配，
另一个是协作性改进
支持项目设置成保存为某一旧版本方便和旧的LabVIEW协作
从源代码比较VI时自动归类相似差异

还有一个NI放在路线图里面的就是NIGEL，一个精调的支持LabVIEW的ChatGPT，可以解释LabVIEW代码，理论上应该也能改进代码，不过看演示还是对话式的，希望以后能做成Office Copilot那种，可以直接操作软件。
目前这个功能似乎还在内测，估计要一段时间才能投入公测。





突然发现labVIEW for Mac在登陆M1支持ARM后不再更新了，一个Mac起家的程序脱离了Mac，只能说世事难料。



LabVIEW 2024 Q3 Features and Changes


	Updated2024-07-16
	2 minute(s) read
		LabVIEW
		User Manual
Released July 2024
Preview Feature: .NET Core (8.0) Support in LabVIEW

LabVIEW 2024 Q3 provides limited support for loading and running .NET Core (8.0) assemblies on Windows, including:
	Enabling constructor nodes, property nodes, and invoke nodes to work with .NET Core (8.0)
	Supporting the following four data types: 
		int
		string
		bool
		char
To enable .NET Core (8.0) support in LabVIEW 2024 Q3, navigate to Tools» Options, select the Preview Featurescategory, and select the Enable .NET Core (8.0) Supportcheckbox.
Saving All VIs in a Project for a Previous Version of LabVIEW

You can use the new Save Versionoption, available in the Propertiesdialog box of properties, libraries, and classes, to configure LabVIEW to save all VIs for a previous version of LabVIEW. If a VI contains features not compatible with the designated version, LabVIEW displays a warning and saves the VI for the earliest version that supports all features in that VI.
Improvements to Comparing VIs

	You can now highlight an item in the differences list or details list with a single click.
	You can use the left and right arrow keys to move between the differences list and the details list, and you can use the up and down arrow keys to move through the differences and details.
	In the Differencesdialog box, a difference or detail appears italicized if it involves only front panel or block diagram cosmetic changes.
	The diagrams can automatically scale to fit an entire difference.
	You can swap the positions of the compared VIs by selecting More commands» Swap VI Positionsin the Differencesdialog box.

来自 <https://www.ni.com/docs/en-US/bundle/labview/page/labview-2024q3-changes.html> 


以下SPB大包的下载地址以及RF的下载地址

Offline Installer 64bit
Software Platform Bundle 2024 Q1
Name	Checksum	File Size
2024 Q1	(MD5) d2112118119e7a7b3e7716a40a53f745	46.58 GB
	(SHA256) 82126e006f09f5df52a4926a613abeb49b0d89419c75f3c69123f5777c8a1dbf

来自 <https://www.ni.com/en/support/downloads/software-products/download.software-platform-bundle.html#521708> 
https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle/24.5/offline/ni-software-platform-bundle_24.5.0.49229-0+f77_offline.iso

Offline Installer 32bit
Software Platform Bundle 2024 Q1
Name	Checksum	File Size
2024 Q1	(MD5) 606cd0aaaef273f2b8a71c518e458cba	47.71 GB
	(SHA256) d346ace3b03d72ba3ea1a94a2db8c15a9def6c69ad8171eeb958ce6e053ac958

来自 <https://www.ni.com/en/support/downloads/software-products/download.software-platform-bundle.html#521709> 
https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle-x86/24.5/offline/ni-software-platform-bundle-x86_24.5.0.49229-0+f77_offline.iso

Offline Installer 32bit chs
Software Platform Bundle 2024 Q1
Name	Checksum	File Size
2024 Q1	(MD5) f14299f5750ebd7b1f414e40ad3f01d7	48 GB
	(SHA256) 7e5d8aeb6aeb8d91b15e7d22f9e578fafc27337bda297a4651c3a21b52921836

来自 <https://www.ni.com/en/support/downloads/software-products/download.software-platform-bundle.html#521579> 

https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle-x86-zh-cn/24.5/offline/ni-software-platform-bundle-x86-zh-cn_24.5.0.49229-0+f77_offline.iso


NI Linux Real-Time Offline Installation Support 2024 Q3
Name	Checksum	File Size
2024 Q3	(MD5) 96f957d942133453d3a061ad8c05379e	8.92 GB
	(SHA256) b662f6c459ca85dce14f5339c7359ad6b42335d498888b7851d385acad541b64

来自 <https://www.ni.com/en/support/downloads/software-products/download.ni-linux-real-time-offline-installation-support.html#544209> 
https://download.ni.com/support/nipkg/products/ni-l/ni-linux-rt-offline-installation-support-24.5/24.5/offline/ni-linux-rt-offline-installation-support-24.5_24.5.0_offline.iso

Offline Installer
NI-USRP 2023 Q3
Name	Checksum	File Size
2023 Q3	(MD5) fb4f7a04b7f73ac34ce7257f32ba21f6	6.67 GB
	(SHA256) 0f6e0f91002ca19dc5919159e0d6d5b284900160ac53137703ce2970366e60d8

来自 <https://www.ni.com/en/support/downloads/drivers/download.ni-usrp.html#484354> 
https://download.ni.com/support/nipkg/products/ni-u/ni-usrp/23.5/offline/ni-usrp_23.5.0_offline.iso

Offline Installer
NI-RFSA 2024 Q3
Name	Checksum	File Size
2024 Q3	(MD5) 9d99c650ae063fa319314a2ae4a6c360	4.28 GB
	(SHA256) f4c334b0e270901b7dc72e5eaca111414989ed6209138969580d434aa4a6f62f

来自 <https://www.ni.com/en/support/downloads/drivers/download.ni-rfsa.html#544242> 
https://download.ni.com/support/nipkg/products/ni-r/ni-rfsa/24.5/offline/ni-rfsa_24.5.0_offline.iso

Offline Installer
NI-RFSG 2024 Q3
Name	Checksum	File Size
2024 Q3	(MD5) 70f2d7eb866307bc755e8ec184cd1ea0	5.16 GB
	(SHA256) 1906e9e4576d490c88b0b9bee27b4de7ac940a548627c111476bb019c8860e91

来自 <https://www.ni.com/en/support/downloads/drivers/download.ni-rfsg.html#544081> 
https://download.ni.com/support/nipkg/products/ni-r/ni-rfsg/24.5/offline/ni-rfsg_24.5.0_offline.iso


Offline Installer
RFmx 2024 Q3
Name	Checksum	File Size
2024 Q3	(MD5) 7a3a5d0ac52b907cb85cd7430684303e	3.76 GB
	(SHA256) d5d01a93695b2eb2905b2fba47797daf4041cc65f8b2e0a7b352806cd8585c00

来自 <https://www.ni.com/en/support/downloads/software-products/download.rfmx.html#544241> 
https://download.ni.com/support/nipkg/products/ni-r/ni-rfmx-suite/24.5/offline/ni-rfmx-suite_24.5.0.49290-0+f138_offline.iso