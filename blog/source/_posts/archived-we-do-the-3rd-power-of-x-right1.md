---
title: WE DO The 3rd Power of X RIGHT(1)
id: 27
categories:
  - Uncategorized
date: 2009-03-24 11:57:08
tags:
---

<div id="msgcns!866B8F96A2761BBE!1285" class="bvMsg">

我们常常有这样一个错觉，在LabVIEW里面使用文本性的代码往往执行效率不如原生的框图高，究竟是不是这样呢？ <p>我们可以看看下面这个例子，如何才能最快的在LabVIEW里计算出X的三次方： <p>首先我们看看几种计算立方常用的办法（对啦，茴香豆有几种写法啊？） <p>1：LabVIEW math选版的幂函数VI <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b65d6b700b3c.png?w=128 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b65d6b700b3c.png)  <p>2：表达式节点的power函数 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b95d74f76c31.png?w=154 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b95d74f76c31.png)  <p>3：用乘法VI连乘（简单好用就是硬道理） <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b125d7c42446a.png?w=159 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b125d7c42446a.png)  <p>4：对啦！连乘而已，表达式节点一样能搞定 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b195d.png?w=154 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b195d.png)  <p>为了测试出到底每种花了多少时间，我们首先记录下算法计算100，000次所花的时间，然后为了消除单次计数的误差，我们循环100次然后平均，最后得出每种算法花费的时间。 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b165d267f1184.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b165d267f1184.png)  <p>下面是程序运行的结果，为了保证不互相影响，所有VI都提前打开并运行一次，以确保内存都已分配，结果如下图 <table border="0" cellspacing="0" cellpadding="0"> <tbody> <tr> <td width="72">  <td width="72">连乘 <td width="72">幂运算 <tr> <td>公式节点 <td>28.84 <td>50.8 <tr> <td>框图函数 <td>34.4 <td>49.55</tr></td></tr></tbody></table> <p>  <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b235d169e6f3f.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b235d169e6f3f.png)  <p>可以看出来，**<font color="#ff0000">LabVIEW 执行文本代码和框图代码效率基本相同，而且改进算法的影响要远远大于代码的表现形式。</font>** <p>附程序执行截屏一张，大图杀猫！ <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b35d5386b4f2.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b35d5386b4f2.png)  
</p></p></p></div>