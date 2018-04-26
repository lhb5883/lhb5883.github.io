---
title: WE DO THE 3RD POWER OF X RIGHT(2)+LabVIEW Unit Test Framework Toolkit 1.0试用
id: 26
categories:
  - Uncategorized
date: 2009-03-27 08:53:18
tags:
---

<div id="msgcns!866B8F96A2761BBE!1316" class="bvMsg">

上回我们说到<strike>茴香豆有四种写法</strike>X的立方已经有四种办法可以搞定，下面我们来看看更多得办法~ <p>使用公式节点也可以 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image2.png?w=149 "image")](http://lhb5883.files.wordpress.com/2009/03/image2.png)  <p>M脚本也可以 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5.png?w=211 "image")](http://lhb5883.files.wordpress.com/2009/03/image5.png)  <p> <p>微软的.NET也可以 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image8.png?w=137 "image")](http://lhb5883.files.wordpress.com/2009/03/image8.png)  <p>如果我们都使用同样的算法，到底这几种接口有没有不同，那种效率更高呢？ <p>我们还是用事实说话： <p>首先有请 LabVIEW Unit Test Framework Toolkit 1.0 for LabVIEW 8.6.1 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image11.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image11.png)  <p>安装好以后我们就可以对LabVIEW VI进行自定义的测试了 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image14.png?w=265 "image")](http://lhb5883.files.wordpress.com/2009/03/image14.png)  <p>我们来回顾一下程序代码这里我把循环次数都变为控件 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image18.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image18.png)  <p>然后新建一个测试 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image22.png?w=271 "image")](http://lhb5883.files.wordpress.com/2009/03/image22.png)  <p>配置输入和输出参数 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image26.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image26.png)  <p>别忘了在工程里面配置一下报表 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image31.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image31.png)  <p> <p> <p> <p> <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image35.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image35.png)  <p>点击运行测试就可以让LabVIEW替我们干活了 <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image39.png?w=265 "image")](http://lhb5883.files.wordpress.com/2009/03/image39.png)  <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image43.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image43.png) <p>大功告成~ <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b85d.png?w=238 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b85d.png)  <p>我们来总结一下~ <table border="0" cellspacing="0" cellpadding="0"> <tbody> <tr> <td width="89">  <td width="116">Use LabVIEW Power Function <td width="119">Use Expression Node with Power Function <td width="132">Use Formula Node with Power <td width="105">Use M Script with Power <td width="134">Use Dot NET Power <tr> <td width="89">Calculating Time(ms) <td width="116">0.0004777 <td width="119">0.0004948 <td width="132">0.0005344 <td width="105">0.1214 <td width="134">0.925</td></td></td></td></td></tbody></table> <p>  <p>从表格和下图可以看出**<font color="#ff0000">LabVIEW的原生节点和框图效率都还不错，使用外部接口和脚本时效率较低。</font>** <p>[![image](http://lhb5883.files.wordpress.com/2009/03/image5b45d.png?w=300 "image")](http://lhb5883.files.wordpress.com/2009/03/image5b45d.png) <p>另付LabVIEW Unit Test Framework Toolkit的测试报告： 

# The 3rd Power of X
Time: 2009-3-27 14:54:04
Operator: lhb
Operating System: Windows NT 5.1
LabVIEW Version: 8.6.1 (en)

## Test Summary
0 Test Errors
0 Tests Failed
0 Tests Skipped
5 Tests Passed
Time elapsed: 00:00:36

## Test Results

### Failed
None.

### Passed
 <table border="1"> <tbody> <tr> <th>Test Name <th>Test Location <th>VI Name <th>Test Cases <th>Duration [s] <th>Code Coverage [%] <th>Requirements <tr> <td>[Use LabVIEW Power Function.lvtest](#Link0) <td>My Computer/LabVIEW Block Diagram <td>Use LabVIEW Power Function.vi <td>1 <td>5.77 <td>100.0 <td>  <tr> <td>[Use Expression Node with Power Function.lvtest](#Link1) <td>My Computer/Expression Node <td>Use Expression Node with Power Function.vi <td>1 <td>5.91 <td>100.0 <td>  <tr> <td>[Use Formula Node with Power.lvtest](#Link2) <td>My Computer/Fomula Node <td>Use Formula Node with Power.vi <td>1 <td>6.20 <td>100.0 <td>  <tr> <td>[Use M Script with Power.lvtest](#Link3) <td>My Computer/M SCRIPT <td>Use M Script with Power.vi <td>1 <td>2.03 <td>100.0 <td>  <tr> <td>[Use Dot NET Power.lvtest](#Link4) <td>My Computer/Dot NET <td>Use Dot NET Power.vi <td>1 <td>1.77 <td>100.0 <td> </td></td></td></tr></td></td></td></td></td></tr></th></th></tbody></table> 

## Test Details
**<a>1\. My Computer
1.1\. LabVIEW Block Diagram
1.1.1\. Use LabVIEW Power Function.lvtest
</a>** <table border="0"> <tbody> <tr> <td>VI Under Test: <td>C:Documents and SettingslhbDesktopInterface TestUse LabVIEW Power Function.vi <tr> <td>Result: <td>Passed <tr> <td>VI Timestamp: <td>2009-3-27 11:59:53 <tr> <td>VI Revision: <td>10 <tr> <td>Test Started: <td>2009-3-27 14:53:27 <tr> <td>Test Duration: <td>00:00:06 <tr> <td>Code Coverage: <td>100.0 % <tr> <td>Setup VI: <td>  <tr> <td>Teardown VI: <td> </td></td></tr></td></tr></td></td></tr></td></tr></tbody></table> 

1.  Test Case 1: Passed**<a>1.2\. Expression Node
1.2.1\. Use Expression Node with Power Function.lvtest
</a>** <table border="0"> <tbody> <tr> <td>VI Under Test: <td>C:Documents and SettingslhbDesktopInterface TestUse Expression Node with Power Function.vi <tr> <td>Result: <td>Passed <tr> <td>VI Timestamp: <td>2009-3-27 11:59:53 <tr> <td>VI Revision: <td>6 <tr> <td>Test Started: <td>2009-3-27 14:53:33 <tr> <td>Test Duration: <td>00:00:06 <tr> <td>Code Coverage: <td>100.0 % <tr> <td>Setup VI: <td>  <tr> <td>Teardown VI: <td> </tr></tr></td></td></td></td></td></tbody></table> 

**<a>1.3\. Fomula Node
1.3.1\. Use Formula Node with Power.lvtest
</a>** <table border="0"> <tbody> <tr> <td>VI Under Test: <td>C:Documents and SettingslhbDesktopInterface TestUse Formula Node with Power.vi <tr> <td>Result: <td>Passed <tr> <td>VI Timestamp: <td>2009-3-27 13:56:38 <tr> <td>VI Revision: <td>12 <tr> <td>Test Started: <td>2009-3-27 14:53:40 <tr> <td>Test Duration: <td>00:00:06 <tr> <td>Code Coverage: <td>100.0 % <tr> <td>Setup VI: <td>  <tr> <td>Teardown VI: <td> </tr></td></td></tr></td></tr></tbody></table> 

**<a>1.4\. M SCRIPT
1.4.1\. Use M Script with Power.lvtest
</a>** <table border="0"> <tbody> <tr> <td>VI Under Test: <td>C:Documents and SettingslhbDesktopInterface TestUse M Script with Power.vi <tr> <td>Result: <td>Passed <tr> <td>VI Timestamp: <td>2009-3-27 14:19:42 <tr> <td>VI Revision: <td>11 <tr> <td>Test Started: <td>2009-3-27 14:53:58 <tr> <td>Test Duration: <td>00:00:02 <tr> <td>Code Coverage: <td>100.0 % <tr> <td>Setup VI: <td>  <tr> <td>Teardown VI: <td> </td></td></td></tbody></table> 

**<a>1.5\. Dot NET
1.5.1\. Use Dot NET Power.lvtest
</a>** <table border="0"> <tbody> <tr> <td>VI Under Test: <td>C:Documents and SettingslhbDesktopInterface TestUse Dot NET Power.vi <tr> <td>Result: <td>Passed <tr> <td>VI Timestamp: <td>2009-3-27 11:59:53 <tr> <td>VI Revision: <td>12 <tr> <td>Test Started: <td>2009-3-27 14:54:01 <tr> <td>Test Duration: <td>00:00:02 <tr> <td>Code Coverage: <td>100.0 % <tr> <td>Setup VI: <td>  <tr> <td>Teardown VI: <td> </td></td></td></tbody></table> 

</p></p></p></p></p></p></p></p></div>