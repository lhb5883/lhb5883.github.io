---
title: LabVIEW 2010图标编辑器与库技巧一则
id: 4
categories:
  - LabVIEW
date: 2010-09-02 01:21:08
tags:
---

<div id="msgcns!866B8F96A2761BBE!1592" class="bvMsg">

LabVIEW 2009时一个很方便的改进是图表编辑器支持图层,2010版本里又大幅强化了不少:

例如支持图层的复制粘贴,自定义图表模板和图例.

[![image](http://lhb5883.files.wordpress.com/2010/09/image5b25d1547d36d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image5b25d1547d36d.png)

对于库(包含LabVIEW Class, X Control)等来说一个很方便的特性是可以批量修改库中VI(包含自定义控件)的模板

通过这一点我们可以简化图标设计的工作:

[![image](http://lhb5883.files.wordpress.com/2010/09/image5b55d7c1b91c0.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image5b55d7c1b91c0.png)

1.首先设计库图标模板:

在库上右键,选择属性,点击编辑图标

[![image](http://lhb5883.files.wordpress.com/2010/09/image5b85d419b7831.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image5b85d419b7831.png)

a)首先选择库模板

[![image](http://lhb5883.files.wordpress.com/2010/09/image5b115d5b4326c9.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image5b115d5b4326c9.png)

b)填充颜色

[![image](http://lhb5883.files.wordpress.com/2010/09/image141df56dac.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image141df56dac.png)

C)编辑文字

[![image](http://lhb5883.files.wordpress.com/2010/09/image17.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image17.png)

点击OK返回库属性,再点击OK提交图标,LabVIEW提示是否应用至库中其他VI,选择YES

[![image](http://lhb5883.files.wordpress.com/2010/09/image202fed776d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image202fed776d.png)

2 编辑VI图标:

此时库中VI图标包含如下图层

[![image](http://lhb5883.files.wordpress.com/2010/09/image2374953c08.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image2374953c08.png)

a)首先我们隐藏掉图标编号

[![image](http://lhb5883.files.wordpress.com/2010/09/image266993fb27.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image266993fb27.png)

b）然后选择合适的图标

[![image](http://lhb5883.files.wordpress.com/2010/09/image290ea50997.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image290ea50997.png)

C）填写说明文字

[![image](http://lhb5883.files.wordpress.com/2010/09/image32.png?w=300 "image")](http://lhb5883.files.wordpress.com/2010/09/image32.png)

这样一个图文并茂，风格统一的Icon就轻松完成了，可以看到利用LabVIEW2010的图层功能，加上良好的程序架构，优美的代码就在我们手中。

[![image](http://lhb5883.files.wordpress.com/2010/09/image38.png?w=32 "image")](http://lhb5883.files.wordpress.com/2010/09/image38.png)[![image](http://lhb5883.files.wordpress.com/2010/09/image351e974c55.png?w=32 "image")](http://lhb5883.files.wordpress.com/2010/09/image351e974c55.png)
  </div>