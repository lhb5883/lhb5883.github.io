---
title: 20221210-labview-fonts-fix
date: 2022-12-10 13:21:17
tags:
---

# LabVIEW字体bug终极修正

## 图标编辑器中的文本变得模糊

来自 <https://knowledge.ni.com/KnowledgeArticleDetails?id=kA00Z0000019ZTFSA2&l=zh-CN> 

除了设置控制面板为英文环境，也可以用改INI的方式修正


FontCodePageList=Small Fonts,1252
设置为中文显示

设置为英文字体显示

## 安全字体:
所有中文字体和英文界面字体:FixedSys,Terminal,SegoeUI,tahoma
不能显示的字体:Arial,Calibri,CourierNew,NI7SEG,consolas,Times New Roman,Small Fonts;

## 多字体修复

经过尝试，
可以添加多个字体
对EXE也有效
FontCodePageList=Small Fonts,1252;NI7SEG,1252


用注册表查询系统所有字体，然后追加到LabVIEW的INI文件

## 程序修复

发现LabVIEW读取注册表键值时没法确认键的数量，所以动态增加NumValues的数量直到超过后报错，然后再从大向小尝试直到不报错，就可以刚好把所有键值读取出来。

经过多次整理之后再把字体名称重复的去掉，最后添加配置项到搜索出来的LabVIEW.INI

## 常见Windows字体修复

如果没有其他特殊字体也可以直接给INI添加这一句
FontCodePageList="Andalus,1252;Angsana New,1252;AngsanaUPC,1252;Aparajita,1252;Arabic Typesetting,1252;Arial,1252;Browallia New,1252;BrowalliaUPC,1252;Calibri,1252;Candara,1252;Comic Sans MS,1252;Consolas,1252;Constantia,1252;Corbel,1252;Cordia New,1252;CordiaUPC,1252;Courier New,1252;DFKai-SB,1252;DaunPenh,1252;David,1252;DilleniaUPC,1252;DokChampa,1252;Ebrima,1252;Estrangelo Edessa,1252;EucrosiaUPC,1252;Euphemia,1252;FZShuTi,1252;FZYaoTi,1252;FangSong,1252;FrankRuehl,1252;Franklin Gothic Medium,1252;FreesiaUPC,1252;Gabriola,1252;Gautami,1252;Georgia,1252;Gisha,1252;Impact,1252;IrisUPC,1252;Iskoola Pota,1252;JasmineUPC,1252;KaiTi,1252;Kalinga,1252;Kartika,1252;Khmer UI,1252;KodchiangUPC,1252;Kokila,1252;Lao UI,1252;Latha,1252;Leelawadee,1252;Levenim MT,1252;LiSu,1252;LilyUPC,1252;Lucida Console,1252;Lucida Sans Unicode,1252;MV Boli,1252;Malgun Gothic,1252;Mangal,1252;Microsoft Himalaya,1252;Microsoft JhengHei,1252;Microsoft New Tai Lue,1252;Microsoft PhagsPa,1252;Microsoft Sans Serif,1252;Microsoft Tai Le,1252;Microsoft Uighur,1252;Microsoft YaHei,1252;Microsoft Yi Baiti,1252;Miriam,1252;Miriam Fixed,1252;Modern,1252;Mongolian Baiti,1252;MoolBoran,1252;Narkisim,1252;Nyala,1252;Palatino Linotype,1252;Plantagenet Cherokee,1252;Raavi,1252;Rod,1252;Roman,1252;STCaiyun,1252;STFangsong,1252;STHupo,1252;STKaiti,1252;Sakkal Majalla,1252;Script,1252;Segoe Print,1252;Segoe Script,1252;Segoe UI,1252;Shonar Bangla,1252;Shruti,1252;SimHei,1252;SimSun-ExtB,1252;Simplified Arabic,1252;Simplified Arabic Fixed,1252;Small Fonts,1252;Small Fonts,1252;Sylfaen,1252;Tahoma,1252;Times New Roman,1252;Traditional Arabic,1252;Trebuchet MS,1252;Tunga,1252;Utsaah,1252;Vani,1252;Verdana,1252;Vijaya,1252;Vrinda,1252;Webdings,1252;Wingdings,1252"

## 安装

修正程序的源代码已提交github
https://github.com/lhb5883/LabVIEWFontsFix

可以在VIPM中搜索font找到LabVIEW Fonts fix 安装
安装好以后重启labVIEW，在LabVIEW的Tools菜单选择Fix Fonts…再重启LabVIEW就可以正常调用字体了。

 