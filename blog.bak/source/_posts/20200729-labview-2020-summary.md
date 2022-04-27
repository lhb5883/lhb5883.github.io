---
title: 20200729-labview-2020-summary
date: 2020-07-29 20:05:46
tags: labview
---
# LabVIEW 2020 发布后的一些吐槽汇总

## LabVIEW 2020 离线镜像下载出错的解决办法

NI的官网使用CloudFlare的CDN加速，国内使用的是百度云加速，因此继承了百度不靠谱的特质，经常发现下下来的hash值和NI官方给的hash值对不上。
这种情况下推荐重新下载一遍，有时候hash就能对上了。
如果反复下载之后，几次的hash都对不上，这时候就可以用变通的办法来处理。
解压缩离线的ISO镜像后
目录下会有Install.exe,一些DLL支持文件，目录有以下三个：
	1. bin（安装支持文件包含了NI包管理器和.net安装环境）
	2. feeds（目录下包含子目录如ni-488.2，再下一层有Packages文件）
	3. Pool（包含了实际的nipkg安装包）

Packages文件是纯文本的，里面包含了Pool目录下的nipkg文件的一些信息。

Architecture: windows_all
CompatibilityVersion: 0
Conflicts: ni-package-manager
Description: Package for displaying the IVI Foundation Inc. License Agreement
DisplayName: IVI Foundation Inc. License Agreement
DisplayVersion: 20.0.0
EulaTitle: IVI
Filename: ../../pool/eula-ivi_20.0.0.49153-0+f1_windows_all.nipkg
Homepage: http://www.ni.com
MD5Sum: abdd1d7965acc3749f5d80adec7bac5b
MD5sum: abdd1d7965acc3749f5d80adec7bac5b
Maintainer: National Instruments <support@ni.com>
OsSupport: WINDOWS_7_SP1_32BIT WINDOWS_7_SP1_64BIT WINDOWS_81_32BIT WINDOWS_81_64BIT WINDOWS_10_32BIT WINDOWS_10_64BIT WINDOWS_EMBEDDED_STANDARD_7_SP1 WINDOWS_SERVER_2008_R2_SP1_64BIT WINDOWS_SERVER_2012_R2_64BIT
Package: eula-ivi
Plugin: eula
Priority: standard
Section: Infrastructure
Size: 3944
UserVisible: no
Version: 20.0.0.49153-0+f1

里面比较重要的是Filename和MD5Sum两个字段，可以用来确认nipkg文件是否已经损坏。
为了修复安装包，需要根据这个配置文件把损坏的nipkg文件找出来，然后替换成好的。
目前看来只要是文件名一致的nipkg文件并且没有损坏，hash应该是一致的，所以可以用其他完好安装包里的nipkg文件进行替换。
经过我实验，Pool里面将损坏的nipkg文件替换为正常的nipkg文件，安装包就可以正常安装使用。

PS:
另外在C:\Program Files\National Instruments\NI Package Manager下有一个nipkg.exe可以创建离线安装包，可惜的是不支持校验和修复已经下载好的安装包,希望NI以后可以加上对应的功能。

## NI 驱动下载 2020.05

Peripheral Drivers for Controllers
From <https://www.ni.com/en-us/support/downloads/drivers/download.peripheral-drivers-for-controllers.html> 
NI CompactRIO
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-compactrio.html#311624> 
NI-ELVISmx
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-elvismx.html#305452> 
FlexRIO
From <https://www.ni.com/en-us/support/downloads/drivers/download.flexrio.html> 
PXI Platform Services
From <https://www.ni.com/en-us/support/downloads/drivers/download.pxi-platform-services.html#313433> 
NI R Series Multifunction RIO
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-r-series-multifunction-rio.html> 
NI-488.2
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-488-2.html#305442> 
NI-DAQmx
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-daqmx.html#311818> 
NI-DCPower
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-dcpower.html> 
NI-DMM
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-dmm.html> 
NI-FGEN
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-fgen.html#305449> 
NI-HSDIO
From <http://www.ni.com/en-us/support/downloads/drivers/download.ni-hsdio.html> 
Vision Acquisition Software
From <https://www.ni.com/en-us/support/downloads/drivers/download.vision-acquisition-software.html#305518> 
NI-Industrial Communications for Ethernet/IP
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-industrial-communications-for-ethernet-ip.html#305843> 
NI-Industrial Communications for EtherCAT
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-industrial-communications-for-ethercat.html#311691> 
NI-Industrial Communications for CANopen
From <http://www.ni.com/en-us/support/downloads/drivers/download.ni-industrial-communications-for-canopen.html#311611> 
NI-Industrial Communications for IEC 61850
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-industrial-communications-for-iec-61850.html> 
NI-Industrial Communications for DeviceNet
From <http://www.ni.com/en-us/support/downloads/drivers/download.ni-industrial-communications-for-devicenet.html#311812> 
NI-Industrial Communications for DNP3
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-industrial-communications-for-dnp3.html> 
NI-SCOPE
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-scope.html#305863> 
NI-Serial
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-serial.html#305457> 
NI-SWITCH
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-switch.html> 
NI-Sync
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-sync.html#311813> 
NI-XNET
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-xnet.html#311817> 
NI-VISA
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-visa.html#305862> 
Industrial Controller Device Drivers
From <https://www.ni.com/en-us/support/downloads/drivers/download.industrial-controller-device-drivers.html> 
NI-VirtualBench Application and Driver
From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-virtualbench-application-and-driver.html> 
LabVIEW ELVIS III Toolkit
From <https://www.ni.com/en-us/support/downloads/software-products/download.labview-elvis-iii-toolkit.html> 

## NI 非集成驱动
NI-Digital Pattern Driver

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-digital-pattern-driver.html#320889> 
NI-Digital Pattern Driver 19.0.1
Name	Checksum	File Size
19.0.1	(MD5) 0e9477f71b0f7e23ff34fd44396eaeb8	1.03 GB
	(SHA256) b157150f962b6cd15df4c6879f6e89a568978060f7221a7ab98a8e701dcdb33f

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-digital-pattern-driver.html#320889> 

http://download.ni.com/support/nipkg/products/ni-d/ni-digital/19.0/offline/ni-digital_19.0.1_offline.iso

NI-PXImc

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-pximc.html#339602> 

NI-PXImc 19.0
Name	Checksum	File Size
19.0.0	(MD5) 8018d68d9593a9d7d8ecac68f21386c0	654.29 MB
	(SHA256) 70ee376319886ce472748774d34010d3361d59c485b2ef8125b9f70fa3ea8c13

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-pximc.html#339602> 

http://download.ni.com/support/nipkg/products/ni-p/ni-pximc/19.0/offline/ni-pximc_19.0.0_offline.iso

NI-ATCA

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-atca.html#> 

NI-ATCA 19.5
Name	Checksum	File Size
19.5.0	(MD5) 2be487ba66fd99f794ddbf8f2881ca50	3.9 GB
	(SHA256) 82fa460c4ab257b4d923964814bbbf33d22cbb6d59d8ceb05d81df17c50d9052

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-atca.html#> 
http://download.ni.com/support/nipkg/products/ni-a/ni-atca/19.5/offline/ni-atca_19.5.0_offline.iso

NI-845x Driver Software

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-845x-driver-software.html#346270> 

NI-845x Driver Software 20.0
Name	Checksum	File Size
20.0.0	(MD5) ba5cb91a93268c50132d823ddc9cb0e8	594.72 MB
	(SHA256) 366699b272abf25d59cfaabbdbf20f328630188ad3f7b1bfff3d3812ae07f820

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-845x-driver-software.html#346270> 

http://download.ni.com/support/nipkg/products/ni-8/ni-845x/20.0/offline/ni-845x_20.0.0_offline.iso

NI-SLSC

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-slsc.html#345643> 

NI-SLSC 20.0
Name	Checksum	File Size
20.0.0	(MD5) d9ad63fca2429542213ad1da64ebe8dd	1.03 GB
	(SHA256) 932f54b6b1d238f424bf3236b883f995cdd957fa67d3e7c9daa8b9fac1b80bb9

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-slsc.html#345643> 

http://download.ni.com/support/nipkg/products/ni-s/ni-slsc/20.0/offline/ni-slsc_20.0.0_offline.iso

Digital Systems Development Board Driver for LabVIEW

From <https://www.ni.com/en-us/support/downloads/drivers/download.digital-systems-development-board-driver-for-labview.html#305456> 

Digital Systems Development Board Driver for LabVIEW 2019
Name	Checksum	File Size
2019	(MD5) 9a52c902c6ff623fe42df892c3428995	811.27 MB
	(SHA256) 8f0bb9c789c379048070e9834bbcf325ea21700e28d7b018aea3a50b254c020b

From <https://www.ni.com/en-us/support/downloads/drivers/download.digital-systems-development-board-driver-for-labview.html#305456> 

http://download.ni.com/support/nipkg/products/ni-d/ni-dsdb-2019-drivers-labview-support-x86/19.0/offline/ni-dsdb-2019-drivers-labview-support-x86_19.0.0_offline.iso

NI Linux RT System Image

From <https://www.ni.com/en-us/support/downloads/software-products/download.ni-linux-rt-system-image.html#> 

NI Linux RT System Image 2020.06
Name	Checksum	File Size
2020.06	(MD5) b81cb14684db49e612c15a5e5c37dd47	567.75 MB
	(SHA256) 5cfa03d861c371831e4921a903bc4e4ec3355498d71b478a4261229525e5debd

From <https://www.ni.com/en-us/support/downloads/software-products/download.ni-linux-rt-system-image.html#> 

http://download.ni.com/support/nipkg/products/ni-l/ni-linux-rt-system-image-2020.06/20.1/offline/ni-linux-rt-system-image-2020.06_20.1.0_offline.iso

NI Linux Real-Time Offline Installation Support

From <https://www.ni.com/en-us/support/downloads/software-products/download.ni-linux-real-time-offline-installation-support.html#> 

NI Linux Real-Time Offline Installation Support 20.0
Name	Checksum	File Size
20.0.0	(MD5) afbbd55a649be6716974b838873edac9	3.68 GB
	(SHA256) 43d768e958b3497493a5615d1462c96232bf1410f9c0bf7f45eb18eb7f1140b6

From <https://www.ni.com/en-us/support/downloads/software-products/download.ni-linux-real-time-offline-installation-support.html#> 

http://download.ni.com/support/nipkg/products/ni-l/ni-linux-rt-offline-installation-support-20.0/20.0/offline/ni-linux-rt-offline-installation-support-20.0_20.0.0_offline.iso


VirtualBench Software

From <https://www.ni.com/en-us/support/downloads/drivers/download.virtualbench-software.html#324215> 
VirtualBench Software 18.0
(MD5)
17dcca1927826257b48eaefed0d258b0

From <https://www.ni.com/en-us/support/downloads/drivers/download.virtualbench-software.html#324215> 
http://download.ni.com/support/softlib/VirtualBench/Windows/18.0/NIVirtualBench1800.zip


Functional Safety Editor

From <https://www.ni.com/en-us/support/downloads/drivers/download.functional-safety-editor.html#326204> 

Functional Safety Editor 2018
(MD5)
6d77dc4e227758aeddabe9df674ed006

From <https://www.ni.com/en-us/support/downloads/drivers/download.functional-safety-editor.html#326204> 

http://download.ni.com/support/softlib/reconfigurable_io/Functional%20Safety/2018%20May/FUNCSAFETY2018MAY.exe

FRC Game Tools

From <https://www.ni.com/en-us/support/downloads/drivers/download.frc-game-tools.html#> 


FRC Game Tools 2020
Name	Checksum	File Size
2020	(MD5) 0fd5df9e21e69e2e5a0e1e5f7d60f60a	850.5 MB
	(SHA256) 63da2e87bd66c6003daa2e31283207eecaf2a91dbdae2b060848ad95ab63c094

From <https://www.ni.com/en-us/support/downloads/drivers/download.frc-game-tools.html#> 

http://download.ni.com/support/nipkg/products/ni-f/ni-frc-2020-game-tools/19.0/offline/ni-frc-2020-game-tools_19.0.0_offline.iso

LabVIEW Software for FRC

From <https://www.ni.com/en-us/support/downloads/drivers/download.labview-software-for-frc.html#> 

LabVIEW Software for FRC 2020
Name	Checksum	File Size
2020	(MD5) 2bed0a8236a5dd452c96a019450a9ecf	7.71 GB
	(SHA256) 7e33d9a3d88b34d11af40b3a18656d1d640679ad6c342151fe247d6f15cb9a9e

From <https://www.ni.com/en-us/support/downloads/drivers/download.labview-software-for-frc.html#> 

http://download.ni.com/support/nipkg/products/ni-f/ni-frc-2020-base-suite/19.0/offline/ni-frc-2020-base-suite_19.0.0.49152-0+f0_offline.iso





NI-568x Driver Software

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-568x-driver-software.html#331229> 
NI-568x Driver Software 19.0
(MD5)
fa01656d755cf54d6e27237e573bfc34
https://download.ni.com/support/softlib/RF/NI-568x/NI568X190.zip



NI-5690 Driver Software

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-5690-driver-software.html> 

Filesize: 1501.48 MB

Checksum (MD5): c1710c5a8c82104fc751e46925cf5ea3

http://download.ni.com/support/softlib/RF/NI-5690/NI5690190.zip
NI-mmWave

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-mmwave.html#312718> 

NI-mmWave 19.0
Name	Checksum	File Size
19.0.0	(MD5) 7e0441e39df7f00457d302c54cf315ff	3.35 GB
	(SHA256) 871e69a27107519d309187f9476ce482dd74c179d363d22252155c60f13b5ee9

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-mmwave.html#312718> 

http://download.ni.com/support/nipkg/products/ni-m/ni-mmwave/19.0/offline/ni-mmwave_19.0.0_offline.iso


## NI RF驱动下载 2020.05

RFmx

From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx.html#333458> 

Application Software
	RFmx Waveform Creator
	RFmx SpecAn
	RFmx Demod
	RFmx Noise Figure
	RFmx Phase Noise
	RFmx WLAN
	RFmx Bluetooth
	RFmx NR
	RFmx LTE
	RFmx WCDMA
	RFmx TD-SCDMA
	RFmx EV-DO
	RFmx CDMA2k
	RFmx GSM
Drivers
	NI-RFSG Playback Library

From <https://www.ni.com/pdf/manuals/377996b.html> 





NI-RFSA

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-rfsa.html#344193> 




NI-RFSG

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-rfsg.html#344209>




NI Wireless Test Standards Software - January 2019
http://download.ni.com/support/softlib/RF/NI-RFmx/NI%20Wireless%20Test%20Standards%20Software/2019.01/WTSSSUITE012019.zip
From <http://www.ni.com/download/ni-rfmx-january-2019/8043/en/> 
Filesize: 4711.16 MB
Checksum (MD5): b0d0266e838d0a29da3fba42822da8e1

From <http://www.ni.com/download/ni-rfmx-january-2019/8043/en/> 


Wireless Test Standard Software Readme Files

NI-RFmx Measurement APIs

	NI-RFmx SpecAn 3.0
	RFmx SpecAn
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-specan.html#341840> 
	
	NI-RFmx Noise Figure Runtime 3.0
	RFmx Phase Noise
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-phase-noise.html#334020>
	
	NI-RFmx Demod 3.0
	RFmx Demod
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-demod.html#333892> 
	
	NI-RFmx GSM 3.0
	RFmx GSM/EDGE+
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-gsm-edge-.html#333491> 
	
	
	NI-RFmx WCDMA 3.0
	RFmx W-CDMA/HSPA+
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-w-cdma-hspa-.html#333973> 
	
	
	NI-RFmx LTE 3.0
	RFmx LTE/LTE-Advanced
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-lte-lte-advanced.html#333523> 
	
	RFmx LTE-V2X
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-lte-v2x.html#337828> 
	
	
	NI-RFmx CDMA2k 3.0
	RFmx CDMA2k 19.1
	
	From <http://www.ni.com/download/ni-rfmx-cdma2k-19.1/8368/en/> 
	
	
	NI-RFmx EV-DO 3.0
	RFmx EV-DO
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-ev-do.html#333924> 
	
	
	NI-RFmx TD-SCDMA 3.0
	RFmx TD-SCDMA
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-td-scdma.html#333583> 
	
	
	NI-RFmx Bluetooth 3.0
	RFmx Bluetooth
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-bluetooth.html#333828> 
	
	NI Bluetooth Direct Test Mode 3.0
	Test Toolkit for Bluetooth
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.test-toolkit-for-bluetooth.html#346269> 
	
	
	NI-RFmx WLAN 3.0
	RFmx WLAN
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-wlan.html#333999> 
	
	NI-RFmx NR 3.0
	
	RFmx NR
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-nr.html#333551> 
	

NI-RFSG Playback Library:

	NI-RFSG Playback Library 3.0
	NI-RFSG Playback Library
	
	From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-rfsg-playback-library.html#332845> 
	

NI-RFmx Waveform Creator:

	NI-RFmx Waveform Creator 3.0
	RFmx Waveform Creator
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx-waveform-creator.html#333592> 
	

RF Toolkits:

	NI LabVIEW Modulation Toolkit 18.0
	LabVIEW Modulation Toolkit
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.labview-modulation-toolkit.html#345617> 
	
	
	NI WLAN Toolkit 18.0
	WLAN Test Toolkit
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.wlan-test-toolkit.html#345670> 
	
	
	NI Bluetooth Toolkit 18.0
	Test Toolkit for Bluetooth
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.test-toolkit-for-bluetooth.html#346269> 
	
	
	NI FM-RDS Toolkit 1.0.1
	NI FM-RDS Toolkit 1.0.1
	
	From <http://www.ni.com/download/ni-fm-rds-toolkit-1.0.1/4462/en/> 
	
	
	NI GNSS Simulation Toolkit 3.0
	GNSS Test Toolkit
	
	From <https://www.ni.com/en-us/support/downloads/software-products/download.gnss-test-toolkit.html#333303> 
	
NI-USRP 20.0

From <https://www.ni.com/en-us/support/downloads/drivers/download.ni-usrp.html#346279> 

RFmx 20.0

From <https://www.ni.com/en-us/support/downloads/software-products/download.rfmx.html#> 

USRP 19.5.1
19.5.1	(MD5) 4868bae57b329326ffdced4afb72fce5
(SHA256) 0de26bbe50480d7abe2b0e5f0da2fd5e06ed2dc1790e58d625033c91b6e37b6b	4.63 GB

https://download.ni.com/support/nipkg/products/ni-u/ni-usrp/19.5/offline/ni-usrp_19.5.1_offline.iso
