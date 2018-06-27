---
title: LabVIEW2018_released
date: 2018-05-25 16:08:12
tags:
---

又到了5月份一年一度的NI Week,LabVIEW 2018按期正式发布,值得注意的有两点,

Python调用支持

NXG风格的控件

 

![PythonNode_AddTwoDoubIes.vi Front Panel  File Edit View Project Operate Tools Window Help  Overview: Demonstrates how to call a Python function and pass doubles as arguments.  Requirements: Python 2.7 or 3.6 with the same bitness as LabVIEW.  Instructions:  I. Set the Python version to the version of Python you want to execute code in.  2. Run the VI. You should see the result of adding "a" and "b" in the indicator "a + b".  3. See comments on the block diagram of this VI and in "ExamplePythonModuIe.py" for more  cw eca python no e passes argumentSMidhändIesteturn va ues.  In or  Iona o  Python version  error in (no error)  us code  source  error out  us code  sourc ](.\20180525-LabVIEW2018-released/clip_image001.png)

 

有个大坑,LabVIEW调用的是Python36.dll,导致32bit的LabVIEW只能调32bit的Python,只有64bit的LabVIEW才能调用64bit的Python;绕过的办法是直接用命令行接口调用Python,不过每条命令运行时都要打开Python.exe,运行完之后会关闭Python.

 

 

互连接口选板新增Python子选板，可使用它从LabVIEW代码中调用Python代码。Python选板包 含以下函数：

 • 打开Python会话－用特定版本的Python打开Python会话。

 • Python节点－直接调用Python函数。

 • 关闭Python会话－关闭Python会话。 

注：必须安装Python 2.7或3.6版本以使用LabVIEW Python函数。尽管不支持的 Python版本可以与LabVIEW Python函数一起使用，但NI建议仅使用支持的Python 版本。访问ni.com/info并输入信息代码python，了解更多关于安装Python的 信息。 

 

NXG风格控件 控件选板包含新的NXG风格前面板控件。使用NXG风格的控件，创建LabVIEWNXG风格的前面 板。控件的外观随终端用户运行VI的平台改变。如果将VI迁移到LabVIEW NXG，使用这些控件可以最大限度地减少前面板的失真。

 

LabVIEW 2018新增了错误寄存器以简化启用了并行循环的For循环的错误处理。错误寄存器取代了并行For循环上错误簇的移位寄存器，如以下程序框图所示。 图 3 错误寄存器可自动合并并行循环的错误。在For循环上配置并行循环时，LabVIEW将自动把移位寄存器转换为错误寄存器，从而遵循通过移位寄存器传输错误的最佳实践。

 

针对不同数据类型自定义自适应VI 比较选板新增检查类型子选板。使用“检查类型”VI和函数可强制让自适应VI(.vim)只接受满 足特定要求的数据类型。使用类型专用结构可为指定数据类型自定义自适应VI (.vim)中的代码段。 