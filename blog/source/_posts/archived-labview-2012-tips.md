---
title: LabVIEW 2012 使用心得
id: 261
categories:
  - LabVIEW
date: 2012-11-23 17:42:25
tags:
---

LabVIEW 2012 自8月发布已有3月有余，总结了一些使用中发现的优缺点：

优点：

1.  新加的For循环条件自动索引很方便。2.  新项目向导选项很丰富，模板文档很详尽。3.  新加的Actor Frameworks增加了面向对象的通用架构。4.  可以从NI FTP下载院校系使用权套件的安装镜像，方便批量安装。  

缺点：

1.  启动界面层级太多，找东西不方便。2.  项目向导响应有时候非常迟钝。3.  LabVIEW 2009的字体BUG重出江湖。4.  不打补丁会出现无法退出的情况。  

点评：

这一次LabVIEW更新增加的Actor Framework给LabVIEW提供基于类和对象的架构选择，不过LabVIEW面向对象带来的好处能否超过其成本还需要在实践中验证。

PS：

LabVIEW 字体BUG修正方案

针对LabVIEW图标编辑器，可以考虑关闭系统ClearType（但是字体仍然不对），或者使用我以前写的字体图片

针对LabVIEW环境，目前最治本的办法是将系统非unicode程序语言更换为英文，但是此时LabVIEW里面的中文会乱码，因此对于中国的LabVIEW使用者没有可行性。