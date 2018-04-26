---
title: NI院校套件批量安装技巧一则
id: 264
categories:
  - LabVIEW
date: 2013-09-26 10:31:35
tags:
---

<span style="color:black;font-family:宋体;font-size:10pt;">NI院校套件提供了一个很方便的自动安装功能:
</span>

1.  <span style="color:black;font-family:宋体;font-size:10pt;">可以自动决定安装顺序
</span>
2.  <span style="color:black;font-family:宋体;font-size:10pt;">可以自动确定依赖关系
</span>

<span style="color:black;font-family:宋体;font-size:10pt;">不过美中不足的是安装Xilinx 10.1编译器的时候还需要手动安装,通过修改安装包,我们也可以自动安装Xilinx 10.1编译器
</span>

<span style="color:black;font-family:宋体;font-size:10pt;">复制或解压4张安装DVD，一张驱动DVD，并按照下图命名
</span>

![](http://lhb5883.files.wordpress.com/2013/09/092613_0241_ni1.png)<span style="color:black;font-size:10pt;">
		</span>

<span style="color:black;font-size:10pt;"><span style="font-family:宋体;">下载</span>Xilinx 10<span style="font-family:宋体;">编译器，并解压至:</span>
		</span>

<span style="color:black;font-size:10pt;">\ASLFL13DVD2\Distributions\Xilinx 10
</span>

<span style="color:black;font-size:10pt;"><span style="font-family:宋体;">修改</span>\ASLFL13DVD1\nisuite.xml <span style="font-family:宋体;">第4072~4082行</span>
		</span>

1.  <div style="background:#f4f4f4;"><span style="font-size:9pt;"><span style="color:blue;">&lt;<span style="color:maroon;">distribution</span>
						<span style="color:red;">id</span>="XILINX10"&gt;</span>
				</span></div>
2.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">inputRoot</span>
						<span style="color:red;">suiteVolume</span>="5"&gt;</span>Windows\Xilinx 10\<span style="color:blue;">&lt;/<span style="color:maroon;">inputRoot<span style="color:blue;">&gt;</span>
						</span></span></span></div>
3.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">installOrder<span style="color:blue;">&gt;</span>9998<span style="color:blue;">&lt;/<span style="color:maroon;">installOrder<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
4.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">EULAId<span style="color:blue;">&gt;</span>None<span style="color:blue;">&lt;/<span style="color:maroon;">EULAId<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
5.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">distributionType<span style="color:blue;">&gt;</span>ADE<span style="color:blue;">&lt;/<span style="color:maroon;">distributionType<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
6.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">displayFolderId<span style="color:blue;">&gt;</span>ASLControl<span style="color:blue;">&lt;/<span style="color:maroon;">displayFolderId<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
7.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">name</span>
						<span style="color:red;">language</span>="0009"&gt;</span>Xilinx Compilation Tools 10.1 (Requires Additional Xilinx Compilation Tools DVD)<span style="color:blue;">&lt;/<span style="color:maroon;">name<span style="color:blue;">&gt;</span>
						</span></span></span></div>
8.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">description</span>
						<span style="color:red;">language</span>="0009"&gt;</span>You can install these tools locally or on a remote computer.\n\nUse these compilation tools to compile FPGA VIs on NI hardware containing Virtex-II FPGAs, such as the 781xR, 783xR, and cRIO-910x devices.\n\nLearn more about the FPGA on your NI hardware at ni.com.<span style="color:blue;">&lt;/<span style="color:maroon;">description<span style="color:blue;">&gt;</span>
						</span></span></span></div>
9.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">installOptionSetId<span style="color:blue;">&gt;</span>NoDefault<span style="color:blue;">&lt;/<span style="color:maroon;">installOptionSetId<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
10.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">defaultInstallState<span style="color:blue;">&gt;</span>NoInstall<span style="color:blue;">&lt;/<span style="color:maroon;">defaultInstallState<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
11.  <div style="background:#f4f4f4;"><span style="color:blue;font-size:9pt;">&lt;/<span style="color:maroon;">distribution<span style="color:blue;">&gt;</span>
					</span></span></div>

<span style="color:black;font-family:宋体;font-size:10pt;">替换为
</span>

1.  <div style="background:#f4f4f4;"><span style="font-size:9pt;"><span style="color:blue;">&lt;<span style="color:maroon;">distribution</span>
						<span style="color:red;">id</span>="XILINX10"&gt;</span>
				</span></div>
2.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">distId</span>
						<span style="color:red;">GUID</span>="{C7B4CAC5-4001-475C-967D-DC65C097AA3B}"</span>
					<span style="color:red;">languages</span>=<span style="color:blue;">"0009"</span>
					<span style="color:red;">packageGUID</span>=<span style="color:blue;">"{1BECF03B-48B7-453F-AEB4-2570F837056B}"</span>
					<span style="color:red;">version</span>=<span style="color:blue;">"10.13.0"/&gt;</span>
				</span></div>
3.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">inputRoot</span>
						<span style="color:red;">suiteVolume</span>="2"&gt;</span>Distributions\Xilinx 10\<span style="color:blue;">&lt;/<span style="color:maroon;">inputRoot<span style="color:blue;">&gt;</span>
						</span></span></span></div>
4.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">installOrder<span style="color:blue;">&gt;</span>9998<span style="color:blue;">&lt;/<span style="color:maroon;">installOrder<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
5.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">EULAId<span style="color:blue;">&gt;</span>None<span style="color:blue;">&lt;/<span style="color:maroon;">EULAId<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
6.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">distributionType<span style="color:blue;">&gt;</span>ADE<span style="color:blue;">&lt;/<span style="color:maroon;">distributionType<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
7.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">displayFolderId<span style="color:blue;">&gt;</span>ASLControl<span style="color:blue;">&lt;/<span style="color:maroon;">displayFolderId<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
8.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">name</span>
						<span style="color:red;">language</span>="0009"&gt;</span>Xilinx Compilation Tools 10.1 (Requires Additional Xilinx Compilation Tools DVD)<span style="color:blue;">&lt;/<span style="color:maroon;">name<span style="color:blue;">&gt;</span>
						</span></span></span></div>
9.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">description</span>
						<span style="color:red;">language</span>="0009"&gt;</span>You can install these tools locally or on a remote computer.\n\nUse these compilation tools to compile FPGA VIs on NI hardware containing Virtex-II FPGAs, such as the 781xR, 783xR, and cRIO-910x devices.\n\nLearn more about the FPGA on your NI hardware at ni.com.<span style="color:blue;">&lt;/<span style="color:maroon;">description<span style="color:blue;">&gt;</span>
						</span></span></span></div>
10.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">installOptionSetId<span style="color:blue;">&gt;</span>NoCustomInstall<span style="color:blue;">&lt;/<span style="color:maroon;">installOptionSetId<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
11.  <div style="background:#f4f4f4;"><span style="font-size:9pt;">  <span style="color:blue;">&lt;<span style="color:maroon;">defaultInstallState<span style="color:blue;">&gt;</span>NoInstall<span style="color:blue;">&lt;/<span style="color:maroon;">defaultInstallState<span style="color:blue;">&gt;</span>
								</span></span></span></span></span></div>
12.  <div style="background:#f4f4f4;"><span style="color:blue;font-size:9pt;">&lt;/<span style="color:maroon;">distribution<span style="color:blue;">&gt;</span>
					</span></span></div>

今后安装LabVIEW FPGA时,就可以自动安装编译器了.