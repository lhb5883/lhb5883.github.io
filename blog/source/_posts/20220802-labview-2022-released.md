---
title: 20220802-labview-2022-released
date: 2022-08-02 22:27:10
tags:
---



# LabVIEW 2022 Q3已发布

## 概述

NI在7月底发布了新版的LabVIEW和套件供下载，版本号为2022Q3，22.5，从这个版本开始，软件改为订阅模型，但是不知道以后会不会改成滚动发布，从LabVIEW的另存为低版本来看，还是有独立的版本号以解决兼容性问题。

值得关注的一个大变动是驱动和LabVIEW版本分离，详情可以看新特性中的具体说明。如果用高版本的labview打开和保存了公共VI，低版本打开估计会有问题，默认分离已编译代码应该只是规避了一部分，之前LabVIEW的打包EXE后可以用更高版本Runtime支持应该也是为了这个特性做的准备，怀疑公共库里面不少关键VI应该是封装成了打包库。但是对于需要修改的范例，不知道能不能做到未来2023修改后低版本的2022可以打开，我猜测应该是不行的，毕竟NI现在应该是希望客户一直升级的，现在就是不知道2023版会是原位升级还是会新装一个目录。

 

目前NI的这种订阅服务模式对需要维护客户固定版本的应用不太友好，除非都用SystemLink进行托管，要不然维护多个不同版本LabVIEW Runtime的工作量其实也不小，如果是工厂等没有公网环境下维护代码就更加麻烦。好在NI现在的订阅制是允许使用低版本LabVIEW的，可以规避这个问题，但是对于希望项目开发环境能够保持在一个稳定版本的LabVIEW上，就只能用非订阅制的旧版了。希望NI能把软件的授权改成JetBrains的半订阅制，订购一定时间长度的软件可以保留最初版本的软件激活，NI之前的口风是有一个专门的调试版的授权是永久的。（更新）查看了一下NI官网，调试版授权比LabVIEW一年订阅要略便宜，不过不提供安装媒体，而且看描述需要先购买一个订阅版的服务才行。

NI软件订阅计划

From <<https://www.ni.com/zh-cn/landing/subscription-software.html>> 

 

 

其他小的变化有支持M1的Mac和支持Windows 11，不过对于目前的Windows 11还不算稳定，Bug还是不少，微软自己官方的Windows Server 2022还是基于Windows 10的，并且企业版的LTSC目前也是Windows10，并没有Windows 11的LTSC，我个人还是建议等到Windows 11稳定发布LTSC之后再配合LabVIEW使用。

 

除此之外需要验证LabVIEW 2022 64bit对cRIO的支持是已经做好了还是鸽掉了，不过这一点需要时间安装之后测试，从文档来看，暂时没有官方宣布。（更新根据实际安装测试，64bit下不支持cRIO,支持RT cDAQ）

另外一个缺点是2022默认使用NI网站的在线帮助了，不过好在本地帮助的CHM文件还在，32bit的帮助位于"C:\Program Files (x86)\National Instruments\LabVIEW 2022\help\lvhelp.chm"，64bit的也类似。

经过测试，NI在大包里面集成的版本号低于22.0的驱动都不支持LabVIEW 2022，包括Veristand也是，要等后续的更新了。估计和21版一样等到SP1的时候才能基本补齐。

 

目前看起来在RoadMap里鸽掉的我期待很久的特性有以下几个,希望未来能开发出来：

gRPC驱动远程调用协议支持

LabVIEW 64bit的cRIO支持

Uincode支持

LabVIEW在运行时中动态创建控件

高分屏支持

 

我个人比较期待的是Unicode支持，毕竟从2011之后，字体BUG就一直没修，LabVIEW如果把区域和语言选项如果设置成中文，很多字体是加载不出来的，而设置成英文的话，有可能会删除半个汉字，如果能借着这个机会把这个问题修正了，可以让人舒服不少，不用当2011钉子户了。

高分屏支持也是一样，如果有多显示器并且缩放比例不一致的话，LabVIEW鼠标和菜单经常错位，希望能好好修复一下。

 

长期来看比较重要的的特性其实是gRPC的调用，彻底实现了驱动层的解耦和分布式系统的底层支持，还有一个是运行时动态创建控件，不过这个需要一个NI官方实现数据和控件动态绑定的方法，不知道Data Grid Control是不是就是干这个的

 

另外补充一点，NI把InsightCM卖给了CutForth，其他大规模使用cRIO的场景就不太多了，感觉cRIO有点像Intel的凌动平台，很多搞物联网的都是用Intel的开发板搭出来原型，然后用ARM的板子量产。尤其是Intel收购赛灵思以后，cRIO也换了集成x86核的FPGA，虽然支持了DAQmx，但是成本也变高了，适合走量的场景不多。

 

CUTSFORTH ACQUIRES INSIGHTCM™ FROM NI

 

From <<https://cutsforth.com/insightcm-acquisition-annoucement/>> 

 

 

 

## 新特性

已剪辑自: <https://www.ni.com/docs/zh-CN/bundle/upgrading-labview/page/labview-2022q3-changes.html>

### 在LabVIEW中比较VI

LabVIEW 2022 Q3（基础版、完整版和专业版）的所有版本现在都提供了比较VI的功能，并且不仅限于专业版许可证。

### Python支持

LabVIEW 2022 Q3支持通过Python对象引用句柄使用Python节点。该引用句柄可用于传递Python对象，作为Python节点输入参数或返回类型。

### 选项默认值的改动

在LabVIEW 2022 Q3中，从新文件中分离已编译代码选项的默认值为启用。

### 调用MATLAB函数

可在调用MATLAB函数上设置断点，然后使用步入调试打开MATLAB(R)编辑器执行脚本。如安装了多个版本MATLAB，可右键单击函数并在快捷菜单中选择在MATLAB中打开，指定LabVIEW调用的MATLAB版本。

### Actor.lvclass的uninit方法

在操作者框架中，Actor类新增了Uninit方法（取消初始化）。Actor可重写该方法，释放在执行Pre Launch Init.vi or Actor.vi时获取的资源。即使之前有错误发生，该方法仍然会执行。

### 支持独立于LabVIEW版本的驱动程序/工具包

LabVIEW早期版本的模块、工具包等附加内容都位于LabVIEW目录之下。从LabVIEW 2022 Q3开始，LabVIEW将从LVaddons共享目录加载这些内容。在Windows操作系统上，LVAddons的默认位置是C:\Program Files\NI\LVAddons。请注意，只有一部分NI驱动程序和工具包会随2022 Q3版本安装到此位置。驱动程序或工具包转到LVAddons目录后，无需升级或重新安装即可与新版本的LabVIEW一起使用。

 

贴上路径图作为参考

LabVIEW Roadmap (2022) - NI Community

<https://forums.ni.com/t5/LabVIEW/LabVIEW-Roadmap-2022/td-p/4218319>

|          | Capability                                                   | Upcoming   1-2 Releases | Future   Development |
| -------- | ------------------------------------------------------------ | ----------------------- | -------------------- |
| 项目管理 | Improvements to   workflows with source code control tools   | ✓                       | ✓                    |
|          | LabVIEW VI compare   tool included in all editions   (Base, Full, Pro) | ✓                       |                      |
|          | Driver version   independence from LabVIEW   (no need to update   drivers for every new LabVIEW release) | ✓                       |                      |
|          | Improved LabVIEW   Project Dependency Management             | ✓                       | ✓                    |
|          |                                                              |                         |                      |
| 互操作   | Call Python code   running in virtual environments           |                         | ✓                    |
|          | Deploy Python   scripts to NI Linux RT devices               |                         | ✓                    |
|          | Native gRPC   server/client interfaces in LabVIEW            | ✓                       | ✓                    |
|          | Better integration   with MATLAB® for debugging between environments | ✓                       |                      |
|          | Support for   calling .NET Core Assemblies (.NET 5 or later) |                         | ✓                    |
|          |                                                              |                         |                      |
| 系统支持 | Support for   Windows 11                                     | ✓                       |                      |
|          | Support for MacOS   on Apple M1 devices                      | ✓                       |                      |
|          | LabVIEW RT/FPGA   64-bit module support for CompactRIO       | ✓                       |                      |
|          | Data Communication   additions (SSH API, IPv6 support)       |                         | ✓                    |
|          |                                                              |                         |                      |
| 改进     | Support for   Unicode in the IDE                             | ✓                       | ✓                    |
|          | Introducing Data   Grid Control                              |                         | ✓                    |
|          | Dynamically create   controls at runtime                     |                         | ✓                    |
|          | Improve LabVIEW   IDE experience on high resolution monitors   (e.g. 2560 x 1440) | ✓                       |                      |

 

## 大包下载

Windows 2022 Q3 Professional 64-bit English

Software Platform Bundle 2022 Q3

| Name    | Checksum                                                     | File Size |
| ------- | ------------------------------------------------------------ | --------- |
| 2022 Q3 | (MD5) ce06c4ca6d95ff99a334d0ba6aa2927d   (SHA256) 990fcd6f52a8b57cb7f1d31cee356e99406a047d6e82f87f9e20756a6e2f48c0 | 58.29 GB  |

 

From <<https://www.ni.com/en-us/support/downloads/software-products/download.software-platform-bundle.html#460282>> 

 

<https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle/22.5/offline/ni-software-platform-bundle_22.5.0.49199-0+f47_offline.iso>

 

 

Windows 2022 Q3 Professional 32-bit English

Software Platform Bundle 2022 Q3

| Name    | Checksum                                                     | File Size |
| ------- | ------------------------------------------------------------ | --------- |
| 2022 Q3 | (MD5) c7c80ad9cd6f436a6d38a79ca05ebb3d   (SHA256) 27869760ad84a02ecc0bed4cb8150152aa296b2a30fcbdacd55f18c441df767f | 58.14 GB  |

 

From <<https://www.ni.com/en-us/support/downloads/software-products/download.software-platform-bundle.html#460698>> 

 

<https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle-x86/22.5/offline/ni-software-platform-bundle-x86_22.5.0.49199-0+f47_offline.iso>

 

 

Windows 2022 Q3 Professional 32-bit Simplified Chinese

Software Platform Bundle 2022 Q3

| Name    | Checksum                                                     | File Size |
| ------- | ------------------------------------------------------------ | --------- |
| 2022 Q3 | (MD5) 0bd962fce7a18c0e71f347aa3c9ee1b7   (SHA256) 09402c7abfaccd7e174d0307339eb35897a082d99775fd61dcd7a7a46302a4b6 | 58.36 GB  |

 

From <<https://www.ni.com/en-us/support/downloads/software-products/download.software-platform-bundle.html#460299>> 

 

<https://download.ni.com/support/nipkg/products/ni-s/ni-software-platform-bundle-x86-zh-cn/22.5/offline/ni-software-platform-bundle-x86-zh-cn_22.5.0.49199-0+f47_offline.iso>

 

LabVIEW 2022 Q3 Professional Mac OS English

Checksum(MD5)b474aa15fd54508dfaa05561ab83055b

<https://download.ni.com/support/softlib/labview/labview_development_system/2022%20Q3/502141BB-01M_2022Q3LV-LMPro.iso>

 

NI Linux Real-Time Offline Installation Support 2022 Q3

| Name    | Checksum                                                     | File Size |
| ------- | ------------------------------------------------------------ | --------- |
| 2022 Q3 | (MD5) 39f7aef09d49123ec0ff221b1a0395a2   (SHA256) 142f11ca1c144c93f437733d92e7ab41ed9adf9a79ed2d65a628b0dd3b4a40c7 | 6.78 GB   |

 

From <<https://www.ni.com/en-us/support/downloads/software-products/download.ni-linux-real-time-offline-installation-support.html#460621>> 

 

<https://download.ni.com/support/nipkg/products/ni-l/ni-linux-rt-offline-installation-support-22.5/22.5/offline/ni-linux-rt-offline-installation-support-22.5_22.5.0_offline.iso>