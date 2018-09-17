
title: 配置LabVIEW和TortoiseGit工作
date: 2018-09-17 10:35:22


首先安装git for windows和TortoiseGit,都使用默认安装即可.

主要的工作量是在于设置TortoiseGitMerge和TortoiseGitDiff


![Config git with labview](./20180917-use-labview-with-git\1537152789409.png)


https://ispring-cloud-45.ispringcloud.com/acc/kc75hpYxMDM3NA/s/10374-N2ZHD-doaJL-kBQpK

https://forums.ni.com/t5/Example-Program-Drafts/Source-Code-Control-Using-TortoiseSVN-Subversion-with-LabVIEW/ta-p/3510829

Configuring TortoiseGit for Graphical Diff
​	1. Right-click in Windows Explorer to expose the TortoiseGit options
​	2. Mouse-over 'TortoiseGit>> Settings'
​	3. In the list of settings on the left, select 'Diff Viewer',On the right side of the dialog, select 'Advanced'
​	4. When the 'Advanced diff settings' dialog appears, select 'Add'
​	5. In the dialog that appears, type .vi as the extension
​	6. Where it prompts you for the path to the external program, type the following: "C:\Program Files\National Instruments\Shared\LabVIEW Compare\LVCompare.exe" %mine %base -nobdcosm -nobdpos
​	7. Repeat this operation for the file-type .ctl
Configuring TortoiseGit for Graphical Merge
​	1. Right-click in Windows Explorer to expose the TortoiseGit options
​	2. Mouse-over 'TortoiseGit>> Settings'
​	3. In the list of settings on the left, select 'Merge Tool' under 'Diff Viewer'
​	4. On the right side of the dialog, select 'Advanced'
​	5. When the 'Advanced merge settings' dialog appears, select 'Add'
​	6. In the dialog that appears, type .vi as the extension
​	7. Where it prompts you for the path to the external program, type the following: "C:\Program Files\National Instruments\Shared\LabVIEW Merge\LVMerge.exe" %base %mine %theirs %merged

	8. Repeat this operation for the file-type .ctl

