---
title: 20220425-how-to-choose-a-labview-version
date: 2022-04-25 15:21:05
tags:
---
# 如何选择LabVIEW版本?
## LabVIEW 常见的BUG
* LabVIEW 2010的Dll导入功能有问题,支持目录选择cINTools目录后无法继续.
* LabVIEW 2009字体和语言处理有bug,并且无法绕过.LabVIEW 2009本身容易闪退.
* LabVIEW 2012+字体和语言处理BUG可以通过语言格式设置绕过,但是可能会删半个字,或者计算字符串显示区域出错.
* LabVIEW 2019+中文版安装其他软件时会报RabbitMQ错误.
* DAQMX中文版建立任务时文字描述出错,可能会把输出搞成输入.
* 中文版LabVIEW在计数器任务生成范例和代码是出错,只能生成空VI.
* 中文版RT模块打包RTEXE之后断线
### LabVIEW建议跳过的几个版本
LabVIEW 2009：出了64bit

LabVIEW 2010：换了LLVM编译器

LabVIEW 2016：放弃32bit XP，开始NXG的开发

LabVIEW 2019：开始更换NI Package Manager 支持Linux RT

LabVIEW 2021：放弃Pharlap ETS
### LabVIEW 值得关注的几个版本
LabVIEW 7.1本体无需激活的最后一版

LabVIEW 8.5模块和工具包无需激活的最后一版

LabVIEW 2011个人使用Bug最少的一版

LabVIEW 2015支持XP系统的最后一版

LabVIEW 2018传统安装包的最后一版

LabVIEW 2020支持Pharlap的最后一版

## LabVIEW的VI兼容策略
LabVIEW高版本可以打开低版本VI,目前来说打开VI可以向下兼容到LabVIEW 6,

LabVIEW无法打开高版本的VI

加密VI可以升级版本,但是没有密码的情况下无法降级

另存为前期版本最多可以保存到LabVIEW 8.

## LabVIEW的模块和工具包兼容策略
LabVIEW模块必须和LabVIEW版本一一对应,模块一般对应的是不同的运行目标和对应的编译工具链,所以图像,控制设计仿真,状态图和RT还有FPGA一样都归属于模块.简单的来说能给LabVIEW增加交叉编译功能都属于模块

LabVIEW官方工具包分为两种情况,新版也是一一对应,LabVIEW,旧版有的可以兼容三个版本,有的自动安装到最新版本的LabVIEW里。

VIPM安装的工具包理论上如果没有依赖特定版本的官方模块或者工具包，一般都是可以被高版本的LabVIEW支持的，只是不能被低于编写工具包版本的LabVIEW使用。
## LabVIEW的驱动策略
一般驱动是向下兼容三个版本的LabVIEW，但是依赖特定版本模块的除外。

另外NI的驱动是可以并行选装的，所以安装的驱动越多，后台服务越多，占用的资源也越多。

## LabVIEW的语言和Bit兼容策略
LabVIEW的32bit有六国语言，但同版本只能安装一种语言。

LabVIEW的64bit版只有英文，不过64bit的可以和32bit的同时安装，z共用同一个License

## 结论
### 简单用户
对于英语不好只使用DAQ板卡，不使用RT或者FPGA的用户，可以用LabVIEW2011中文版（或其他值得关注版本）加对应DAQmx。
### 进阶用户
如果必须要使用RT和FPGA，但RT和FPGA部分较为简单，可以确认自身编写的代码没有问题，可以考虑装最新的中文版LabVIEW和RT+FPGA，出现BUG之后再替换为英文版的。
### 学习者
在学习阶段，装一个次新版本的中文版LabVIEW及对应模块，装一个最新英文版和64bit版的LabVIEW及对应模块，驱动安装最新版的，利用向下兼容支持次新版的LabVIEW。
### 资深开发人员
建议全套英文版开发环境，如果有多版本的项目同时开发，可以通过虚拟机分离，一个虚拟机里面最好只装一个对应版本的全套开发软件和驱动。
本机上编写代码装一个LabVIEW 2011，查看代码安装一个最新版的LabVIEW，避免从别的地方接收到的VI无法打开。但是不建议装驱动，因为具体开发还是要在对应版本的环境中比较好。

## 展望
另外多说一句LabVIEW 2021开始64bit官方功能完全和32bit对齐的一版，具备了RT和FPGA模块，不用在64bit中写下位机，32bit中写上位机，等迭代上几年后解决了安装包冲突的问题，以后初学者就可以装一个32bit的中文环境用来学习，同时64bit的英文环境用来开发，入门可能会更方便一些。

