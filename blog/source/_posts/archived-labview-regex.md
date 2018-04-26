---
title: LabVIEW 正则表达式应用
id: 29
categories:
  - Uncategorized
date: 2009-02-19 03:09:02
tags:
---

<div id="msgcns!866B8F96A2761BBE!1204" class="bvMsg">

在传统的文本式编程里，最常用的字符串处理方法就是正则表达式。在LabVIEW里面，虽然也提供了大量的文本处理函数包括查找替换等等，供我们处理字符串。 <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b35d51d3708e.png?w=248 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b35d51d3708e.png)  <p>不过LabVIEW里面也提供了正则表达式这一强大的工具： <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b65d65c188ce.png?w=71 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b65d65c188ce.png) [![image](http://lhb5883.files.wordpress.com/2009/02/image5b95d.png?w=127 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b95d.png) [![image](http://lhb5883.files.wordpress.com/2009/02/image5b125d079d1142.png?w=149 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b125d079d1142.png)  <p>  <p> <p> <p>下面我们看看这个例子，将输入字符串的数字、冒号、小数点保留，其他字符去掉。 <p>使用Case结构和字符串函数： <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b165d3abfef7d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b165d3abfef7d.png)  <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b235d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b235d.png)  <p>然后可以看看用正则表达式实现： <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b275d.png?w=284 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b275d.png)  <p> <p> <p>[![image](http://lhb5883.files.wordpress.com/2009/02/image5b315d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/02/image5b315d.png)  <p>可以看到正则表达式是一个非常强大的工具。推荐两篇文档可以看看 

### 正则表达式30分钟入门教程
 <p>[http://unibetter.com/deerchao/zhengzhe-biaodashi-jiaocheng-se.htm](http://unibetter.com/deerchao/zhengzhe-biaodashi-jiaocheng-se.htm "http://unibetter.com/deerchao/zhengzhe-biaodashi-jiaocheng-se.htm") <p>Introduction to Regular Expressions(MSDN) <p>[http://msdn.microsoft.com/en-us/library/28hw3sce.aspx](http://msdn.microsoft.com/en-us/library/28hw3sce.aspx "http://msdn.microsoft.com/en-us/library/28hw3sce.aspx")<p>
<div style="text-align:left;">LabVIEW 程序下载：
</div>
[http://cid-866b8f96a2761bbe.skydrive.live.com/embedrowdetail.aspx/Public/regular.zip](http://cid-866b8f96a2761bbe.skydrive.live.com/embedrowdetail.aspx/Public/regular.zip)
</p></p></p></div>