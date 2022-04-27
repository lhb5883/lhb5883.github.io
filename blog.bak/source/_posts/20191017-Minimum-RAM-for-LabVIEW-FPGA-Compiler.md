---
title: 20191017-Minimum-RAM-for-LabVIEW-FPGA-Compiler
date: 2019-10-17 11:06:42
tags: LabVIEW
---

# LabVIEW FPGA Vivado 编译器最小内存要求

记得刚开始用LabVIEW FPGA的时候还是在XP下，当时编译时爆内存不足简直是家常便饭。不过在大内存普及的今天我们来看一下到底多少内存足够编译器使用。

 

Xilinx FPGA Chips for National Instruments RIO Devices

From <http://www.ni.com/product-documentation/54514/en/?OpenDocument> 

Minimum System Memory Recommendations for the Vivado Design Suite

From <https://www.xilinx.com/products/design-tools/vivado/memory.html> 

Memory Recommendations Using the ISE® Design Suite 14

From <https://www.xilinx.com/products/design-tools/ise-design-suite/memory.html> 

 

整理出来的内存占用，单位GiB

| FPGA系列          | 典型NI产品型号 | 芯片型号 | 编译器 | 最小内存 | 最大内存 |
| ----------------- | -------------- | -------- | ------ | -------- | -------- |
| Virtex-5          | PXI-7954R      | LX110    | ISE    | 2.1      | 2.9      |
| Virtex-6          | PXIe-5646R     | LX240T   | ISE    | 3.7      | 6.5      |
| Virtex-7          | PXIe-5840R     | VX690T   | Vivado | 5        | 7        |
| Spartan 3         | sbRIO 9642     | XC3S2000 | ISE    | 1.03     | 1.52     |
| Spartan 6         | cRIO-9082      | LX 150   | ISE    | 2.2      | 3.7      |
| Zynq-7000         | sbRIO-9607     | XC7Z020  | Vivado | 1.3      | 1.9      |
| Kintex-7          | PXIe-6592R     | XC7K410T | Vivado | 3        | 5        |
| Kintex Ultrascale | PXIe-7915      | KU060    | Vivado | 7        | 11       |
| Artix-7           | cRIO-9058      | XC7A100T | Vivado | 2        | 3        |

 

 

可以看到编译LabVIEW FPGA基本上有个16G内存就差不多了，除非要同时编译多个bitfile可能需要更大的内存。而Xilinx的Virtex UltraScale XCVU440峰值需要48G内存，这就只有上专业工作站才能满足了，或者考虑在Linux服务器上部署编译服务。