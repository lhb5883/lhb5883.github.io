---
title: LabVIEW和Visual Studio的数据库联接
id: 38
categories:
  - Uncategorized
date: 2008-04-14 09:37:00
tags:
---

<div id="msgcns!866B8F96A2761BBE!793" class="bvMsg">

最近在研究Visual Studio的数据库连接，正好我们的[SW](http://stormywolf.spaces.live.com/)同学写了一个基于LabVIEW的数据库程序就被我厚颜无耻拿来学术研究了：

**首先我们先看看界面：**

这个是他写的LabVIEW程序：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxiV4koJ1Eq2sXTsE11i8ZJRGewFQiztnfPfw7JTG7xKWusFKmn5ACWO2coVgECx6-XO7SojRS0ODKwQT0VB993?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr-rsHPZ9qsTUYK3Bcfks73Qb-WYzW354oRm-XMtpVsxGmC3jCw4Um3GXhqAb4elqN4pWU8B71QfYA?PARTNER=WRITER) 

开发环境：LabVIEW 8.2/8.5

需要LabVIEW 8.5（or Runtime）、Database Connection Tools支持

本人的高仿山寨版：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpykb7c7LqXMZWwBs8ne29EIZa1q2StZAc1xotbRR4vvMv1Twk5RevgZYHJXq6wsMOXmXAXoCsseGA9YU5ClGaOg?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMIzc7sPe8YXm9aDYKhVikAkKl9dITc27FKJuvzj0tWGWiVwhWDBDRXWi-3VeagVuk3rTPuOFZMJjPI026dOmYo?PARTNER=WRITER) 

开发环境：Visual Studio 2008/2005

需要IIS5.1（及以上），.net framework 2.0支持

浏览器支持：Internet Explorer 7.0/8.0 beta1，Firefox 2.0/3.0 beta 5，Safari 3.1

**然后我们再看看程序：**

<font color="#ff0000">数据库的连接</font>：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzgWo2X06OKTBGkcMlUp15FLlFL0l1Apd9AaN3XZHq5N4ikj1bdVyhxOj1jZkaVht-6xurvYrk_Dgt6TlDovXZF?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyZF-5Nvn7HzrSLf1LEZNS-EngM075lS6O4kfEC4VgI6hH_t6tCWGVQt5c6II-xt-2UdznDlkF7zPGmDjDw4lV4?PARTNER=WRITER) 

LabVIEW可以通过DSN连接，也可以通过其他方式。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwMFOCxgwtxx6bBOcpYEoA7hdMFUf4F37dBlkSPuDhZcRrTLdJ1X788FzQV7ZBu4g__wgFRJOOJjN_z-E5aPp_C?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpySP0QEmndfxyDA35Sv2iBH41BNwzTHPtdi2bXgdwh3owYRiUBU2Mn8530yjx65FqLw-oPrCCo6a-gNasAwxBbu?PARTNER=WRITER) 

Visual Studio也是类似的：
 > String connStr = @&quot;Provider=Microsoft.Jet.OLEDB.4.0;Data Source=db1.mdb;User Id=admin;Password=;&quot;;
> OleDbConnection conn = new OleDbConnection(connStr) 

我使用了连接字符串来连接数据库。 <p><font color="#ff0000">数据库搜索</font>都是用SQL来查询： <p>LabVIEW： <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwC28qRpaOuAskfy86qKEv88Iz6e4J1KaSvCR0OMEN_U4jfdZXcgDfBGbbmwYAyewzC7RpOMaeOumuOcXJQdM1D?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwgzO27HK24yQ_j6KkpOiMpB-Fee8wXEVrfu_TKBTsnwuprNTQLWJ1dPGrkKgV0tm9E8nA0B3Jiq5P9fVQb8CWl?PARTNER=WRITER)  <p>Visual Studio： <p>select ID,Problem,Answer,keyw from (select * from [Communication Buses] union select * from [DAQmx/DAQ] union select * from [Instrument Drivers] union select * from [LabVIEW] union select * from [LabWindows/CVI] union select * from [Modular Instruments] union select * from [other softwares] union select * from [others] union select * from [PAC] union select * from [Platform] union select * from [Vision and Motion]) as muti where Problem like '%6251%' or KeyW like '%6251%' <p>数据的解析与显示： <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpymnd9lEnht_-dZMjiQaZzHcZGqxkoVmYibVqP1yDyQwE3vWP5USjdIlG8YcDRmr5AxHSPEq_QFW8WK4fd8FetE?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzUh9RxmHUHlQsQVcZzokKTEOJENxAtuTybqdFW_lN_eXFOpyymoTIgjGZLDZHtSX7LgypP49oYuQ3Tt6599pxJ?PARTNER=WRITER)  <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwdjKgkdEOuUJwK9ScRs89anH-BRU9Ar4lcqK88oqJpXMWfepmojz27i54jPWTXDcgHBpb4uvxWC64VKvDXFoNM?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPjn1n4pr3OoZpHmo82MeLqchHxscFj-DG4V4bQB04gKU2jt1ckYcFtXpurELrpEslP4PbWbwvtHFZ4vkLxzoBN?PARTNER=WRITER)  <p>OleDbDataAdapter sda = new OleDbDataAdapter(SQLQueryString, conn);
DataSet ds = new DataSet();
sda.Fill(ds);
GridView1.DataSource = ds.Tables[0].DefaultView;
GridView1.DataBind(); <p>[![image](http://byfiles.storage.msn.com/y1pf3H7KtzkuRGFzf7nu6U_SeaBmQsqJZNNI9rOqaDSe1wyUJlk5D4NBNNbYWaLZtDBJrcRJBIv4vI?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr8zGIRo3qg_bYE6ilLd57GsOmq299QvsIR_ZD86qVDK_QjBa_fnh6tMVue00UudhdWlozNI_TY68A?PARTNER=WRITER)  <p>小结：可以看到LabVIEW和Visual Studio都提供了很方便的数据库连接接口，使用的方法也比较类似。 <p>区别就是LabVIEW编程可以很方便的利用状态机，而使用C#就要利用事件，这个并没有优劣之分，主要看个人习惯。 <p>因此这次的对比证明了LabVIEW和Visual Studio相比数据库的开发能力差不多，关键还是在开发者的开发习惯。 <p>  <p>=========================以下是纯洁的分割线================================ <p>**<font color="#ff0000">如何在XP下配置IIS和ASP。net 2.0 </font>** <p><font color="#000000">1：安装IIS：</font> <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxVDZ7BNPfyTAO1g1Cd9RgNPSK5K75wJ5y7kxWWxSSCLbxgVIZk_-7zXd6dmegGr7gVfOt162jIx-CvI2N_S4f1?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr85tot0mo1Q95NcyIQgle5vrAwAbzCiaClOX9MRQTkEgsOBSHME-4MDWKsaX3u0OwVIBC2GaHDJqw?PARTNER=WRITER)  <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzfYzTugeeG0B8_MgWgd81J8wbSM6x5_qkFxRXVJIjBHICmcTrZb6WI_DdM6NF6AxUloeu743yltKZWQ44XjfOu?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzFV87Q5V6h-zClFZXrg085n7WkeRGjB6Rbp5FjVBnGClBcA33bL-4_WMIm0EmHGbm0GurVC8Q4TBfV_Hfvit_0?PARTNER=WRITER)  <p>基本上一路下一步即可，提示插入XP光盘就插进去。 <p>2安装。net framework2.0： <p>下载链接： <p>[http://www.microsoft.com/downloads/details.aspx?displaylang=zh-cn&amp;FamilyID=0856eacb-4362-4b0d-8edd-aab15c5e04f5](http://www.microsoft.com/downloads/details.aspx?displaylang=zh-cn&amp;FamilyID=0856eacb-4362-4b0d-8edd-aab15c5e04f5 "http://www.microsoft.com/downloads/details.aspx?displaylang=zh-cn&amp;FamilyID=0856eacb-4362-4b0d-8edd-aab15c5e04f5") <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzezCn7VvzX937E6uGTHNCCn_LPBvwdHjKE7Bvw3mlp-LIX9etCAAKEbIeBTskKLYHhtCp74z8pnZ3yccKntw5_?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwMF7nrOK3OdGYuKbUrxH-5tp-aU4EFJmHLyyrRtSAl-X6072fFQWGhLJM59YGziPqd4gevupLTeG6UgNiySlNv?PARTNER=WRITER)  <p>这个也是一路下一步。 <p>3 配置IIS和ASP。net <p>[![clip_image002](http://by2.storage.msn.com/y1p8NjIsGi7lpwghfT7qH13uHr4hJbZ_655Jg2G15ZEc8KURrfwHYeZYdmcCRFlBDD7s0AqOcbI4zWouWMG5sIHpkgvvVugTrTU?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOuK3E8vElf524vNo7L96Al-WHY4RhiG9WizlpoiWpOyc9qarMj9ZC95_2qZYGvkqxyt_s9FtWTgwAe6Xfk3szT?PARTNER=WRITER) <p>首先配置主目录： <p>[![clip_image002[4]](http://by2.storage.msn.com/y1p8NjIsGi7lpzE49wFDunldELaHobS9AA8NpHyr3o5EiCmvonORqb9rABwbwEMuP6YUqsqHZUi_gucJ_KrwtCXh_2zpVTjIX9v?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwRH0R9u5SFZsznI6HY7VrMu4CnxbfbZUqkKz_Vv1_7rGNcGd503LPWp0hLpgDMW3sdB1bls2CrzBfiyutdAFWR?PARTNER=WRITER) <p>然后配置ASP。net： <p>[![clip_image002[6]](http://by2.storage.msn.com/y1p8NjIsGi7lpw_XdK8DNb80wjofB6CUcWgv_sMPmDjA_7ZX7gfint7B0QccppCB3ZLYQbIezbXhGA_ILXQLJ0Q9aIKM373bXsy?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzM00JBJt8m05zZ7sl2ZfOiaNJHTLA0VW6f7iT470mg_ocCdJ8yePjelb2CD3e4ebyN0iFyEOLjjm-Mjr-T-O-W?PARTNER=WRITER) <p>然后回到主目录这一页配置ASPX关联： <p>[<a href="http://by2.storage.msn.com/y1p8NjIsGi7lpwRH0R9u5SFZsznI6HY7VrMu4CnxbfbZUqkKz_Vv1_7rGNcGd503LPWp0hLpgDMW3sdB1bls2CrzBfiyutdAFWR?PARTNER=WRITER">![clip_image002[4]](http://by2.storage.msn.com/y1p8NjIsGi7lpzE49wFDunldELaHobS9AA8NpHyr3o5EiCmvonORqb9rABwbwEMuP6YUqsqHZUi_gucJ_KrwtCXh_2zpVTjIX9v?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpweO_Raw-S1yo9VgHKVd_SioObI6tTYA3y2xpA8B7kQuJX2zHMnr08ix4UBIKAEYdYaA7_1IrL7fIHsaCG_w4h4?PARTNER=WRITER)![clip_image002[8]](http://by2.storage.msn.com/y1p8NjIsGi7lpzGegUvTnzx2dQYxBCW4ErigqgaDDQ9dv1rpxqs_O02hyn9GDRexvconsuaQ7mzIVkUtyvnJv3V9aUcx0ExaJ95?PARTNER=WRITER)</a> <p>再添加主页： <p>[![clip_image002[10]](http://by2.storage.msn.com/y1p8NjIsGi7lpyZc-ZNW65n0r860o7lZQfre1DfPBYwNZWJENpjBZqIrRM_TDC_OSql8z0C2uDvWiBT8tL_9hlngperkcFSfBp5?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwNJF49vYCiIU7cH9xRpOSjbzeV4EP_4mooK8FtWNsgD3_xA2sm8S1W8D_0g2Emi-Sv-_uQmXPoGmLFVDYkZRKY?PARTNER=WRITER) <p>4 授权IIS用户： <p>在C:WINDOWSMicrosoft.NETFrameworkv2.0.50727&gt;aspnet_regiis.exe运行GA参数 <p>-ga &lt;user&gt; 为指定的用户或用户组授予权限，使其可以访问 IIS 元数据库和 ASP.NET 使用的其他目录 <p>[![clip_image002[12]](http://by2.storage.msn.com/y1p8NjIsGi7lpzp4LiFzVzKER5Zv3jwhZPvAzyNPPvRvdmTE-1qg0lEGdoIy_yck_mDAzPMiLMYy5OlA-x0xscHeYeSBN4cJHdi?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhODm2fi_rdmcFZkSzcnQWLsdb5SeV58nSGgVR-MbX-jzRuijok9CvRIoevikOZtnNNWNV29hDzmpDtUDezu41P3?PARTNER=WRITER) <p>目标是IWAM打头的那个用户。 <p>[![clip_image002[14]](http://by2.storage.msn.com/y1p8NjIsGi7lpzXj267jt-WJLoaH2SAOcmnGpFZ4KTLXMV2H0L72MMNmDEcbjrI7RBw0xNy4ca384MKEWZHLqal_X48hjvSSoh4?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyu9-FSxAqCM2LvhSnRNT_OWuNYVRLZz692d2LCUl7T6JmPH4O0L0qofybqBLDl1a--TQ-99JLIFXoqcCWj-_Wm?PARTNER=WRITER) <p>5 最后打开防火墙80端口 <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxKxTzM1rQvwZOymZp8EiAJsZfz1SYB6cSY1Qyk3Y1DvS7QhwBUiNeoqNmBRjX_VFBl3u83TvlED31WpXyDBReS?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwPYuPipdQ8EVRSsCHkgBrSrp1RbKIh8ixycGqIApiVrEyO6L-PIisT35K5yIUXilXVgWz5SNS8BuOT6CGozOkr?PARTNER=WRITER)  <p>6 大功告成！ <p>[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwbEbbVmOX-ZoUDQQzV4Mvl19SK07HseVzkfOolMnHOCp8xh8PfKYQwpVlUUcEd7mQS6fSj4EWl5EUnf0igHpGn?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMxe0WHtcOrzvtgtOB5-puP3GdnPRvP8460OHHV3VLDoBDPlYdsRbItrJ-2k4xmOYgsGXqIxabk3iTH15hc5jdX?PARTNER=WRITER)
</p></p></p></p></p></p></p></p></p></p></div>