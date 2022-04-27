---
title: cRIO摧残记（上）
id: 40
categories:
  - Uncategorized
date: 2008-03-20 13:10:29
tags:
---

<div id="msgcns!866B8F96A2761BBE!729" class="bvMsg">

今天我们出场的主角就是它

[![20080320](http://by2.storage.msn.com/y1p8NjIsGi7lpyiv35ZMGRjDFH97ApuuLjq_N0d4Y2I6CBWyGerWDoWYXGSQJ6v-SQdVUiJsrhfo3cBqTezUeah_3h_YcIcEyu4?PARTNER=WRITER)<a href="http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOBp2roWlelbQWmvojenkbYkdVWsGH-9QxQ17C_WqKgu9iWPVXNlRJVAuaLBWgyKylfMotxhGgtQxF7_2YJKm9j?PARTNER=WRITER">![20080320(016)](http://by2.storage.msn.com/y1p8NjIsGi7lpzVG-OYgPDBYECgY-PK1J2cypGztD4_DTL4jKdvyIsQHq-BGn_i-RBakpZSBzgAXcZU7OgJncSLjRomFX2ro_ir?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pwkYDTaroUr8AlLm7yxGGhPSPzzAXI6ZGG1UvW-1FvV9NRPHylaG0BM1pmBeLxhTzOIXjo0aA4yvvrzlhex2-iQ?PARTNER=WRITER)</a>

控制器

[![20080320(002)](http://by2.storage.msn.com/y1p8NjIsGi7lpwqMVWYGGE7XoTglxKBdwIl80sqD4v5QLxnHGAPdVtijw4sQ51RjAud60NruIQbvG4HmjRdDrlwQQDyGEE1IWDs?PARTNER=WRITER)<a href="http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPrN_Lg9UG2HRBxh50ZnyeKruvKcahy77w9M9YdfxwubPOEuJoNPm1Xns9gV_NEl5qeMGBtJ0-Fsr0tdV3z1nZR?PARTNER=WRITER"><a href="http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMXNZYS-tUtOYrFpCkvSsxhxjVfUtQZ8JZyN8wjz3QwSng2Ig2iiQ2lr4UlnEq4yPjEwjmGcuJatu-Oxn_3AkGV?PARTNER=WRITER">![20080320(001)](http://by2.storage.msn.com/y1p8NjIsGi7lpxMT9IiwHp7hNarRHPuuGyNXUp6vBt_lZpoWXihi9d1s8Zq2ASCuSylIWe4vO9zFjpbl4ztPaPdchPQjK_bC7L4?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPrN_Lg9UG2HRBxh50ZnyeKruvKcahy77w9M9YdfxwubPOEuJoNPm1Xns9gV_NEl5qeMGBtJ0-Fsr0tdV3z1nZR?PARTNER=WRITER)</a></a>

[](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPrN_Lg9UG2HRBxh50ZnyeKruvKcahy77w9M9YdfxwubPOEuJoNPm1Xns9gV_NEl5qeMGBtJ0-Fsr0tdV3z1nZR?PARTNER=WRITER) 

  [![20080320(005)](http://by2.storage.msn.com/y1p8NjIsGi7lpyfZuQHyTkUGZisuRYGm8Nw1qkOOtqmDgkEFNUDOMn3P8njdTXTxvolLynBsjql8Ry7GbTXBrkspoS69WW5exTh?PARTNER=WRITER)![20080320(007)](http://by2.storage.msn.com/y1p8NjIsGi7lpwG6YPDORajJ4J10vxvJqovSsnTgYVwaJEvCYTZGsBwWB3GZ7iqdDyDXHcyZAMiXCBEqQ27ZPRyzuCfOO8p2ZeQ?PARTNER=WRITER) ![20080320(006)](http://by2.storage.msn.com/y1p8NjIsGi7lpxFoLJKRZ8EnvOel4CM15y1QeDQ86x7y_eNGz9vUIoB8JR4q2Pd5B4pUM6AsVKMye4-NVMX8jndF6SMsC9ylz4-?PARTNER=WRITER) ](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMXNZYS-tUtOYrFpCkvSsxhxjVfUtQZ8JZyN8wjz3QwSng2Ig2iiQ2lr4UlnEq4yPjEwjmGcuJatu-Oxn_3AkGV?PARTNER=WRITER)

FPGA

[![20080320(003)](http://by2.storage.msn.com/y1p8NjIsGi7lpxm6rQjHpxAUyRZHwFqqKj2xiIUSa9JqhnQ9NUBFPDjcJLlfdcV7zZ6o4BRWrjAY9Ntw-rRRIA64GzcP94a5oHo?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPN6BgjY_twaRGgHUyhBRMEzOltuU3rhn-AOFmifqEyP19xPz4_nfTBRhoC_JfKSHkg8FpUKLz7rtY9DsXM6BrI?PARTNER=WRITER) [![20080320(008)](http://by2.storage.msn.com/y1p8NjIsGi7lpxe1hoL3ruQopVV33hN0RgLnfVJ8ni-vOTm_PJcQIvaktoTQALQj6WRHKrtP0FPRBm3EOOcAN0UcB2Ciq435MKP?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhO1zsKqXWNSAL-36wLmrWc2XAyRLr_abPLLfJjrqyWBNUczZ3_xP_KM6Q8LMDlrjfmrJiggmkcaXJlUyRTywtH6?PARTNER=WRITER) [![20080320(013)](http://by2.storage.msn.com/y1p8NjIsGi7lpw3WQR8vopbcs2jhAwjalY3TbDonp0grz_r0Ma4WrHyR0GirTfwFgoaN9StLM_uPAnRDWZ5iqDgfRogCKp9bgGq?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMe9ZTEkZojH71ZXHUXxIwmCa_L9EwkkwIGj2I7bYUze3IIkzgYJ0GK0ZcdrM1XXipmSoA3sKkogCtcIb5_lm1-?PARTNER=WRITER) 

插上网线通电以后 我们首先打开MAX

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxOOBaCQ74UtHyhSoFyleQyRL1xGboxZze_vXs63sfLdEtkkV6w1bs0rnHb5NmTJYsmHCEhM45VU3e_Z1tUhe-a?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpwd7yL5njGXePy8TMJXDq_D93UWEme6opbsfOlhEWw5gMd2Z52Np3jAPtAYW6Bg7Pg0BxSG9w2XzoBHx4UuJLBf?PARTNER=WRITER) 

在远程系统按F5

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpycIh7VQdnf7URl7puKZEjv7KB6lson7rVwwsMp0BBgbjd3HzTCL04WMB6r_OXTgDvBzBAMhbGVVVt3vJ7XRG40?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxs01qfNwAkKpZF3ROmxXwiIJrbYxWn6BInUFbGpl8peh4u5DFcPtGYNsLsfNwxg4yqH9GqQCs-XvqgUXkX416f?PARTNER=WRITER) 

可以看到已经自动认出来了

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxd5EqvIb0iq4uMFjJIn_w9Y8gcLCGoKE2Yuoh8-hddKDU-X5ox-xVz3tKirXPLwUpYGd9E3GSNGnB78vkQCf4D?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpywaMjt1OSyMRMHZT25NFyJAnYxVWxDimPVrLTiYf6zfmrd55GSKJtQNCvNFAGcXW-V6Leyyl9bkDuGEXulSHtG?PARTNER=WRITER) 

使用前请先摇一摇（误

需要配置一下网络参数

然后给cRIO里面装软件：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpx5lUXJ3-eGJUDgUqNT--JLpgBdTesgi5RbRYyA11Bng-Pexg8ZldweLFd0utOt13UnkpJjsWCj21cIweajRg_J?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzwugoKRjwdTYyeePMGnh7pZ6iuebI2nj38gW1V1zsE1GXdwDo5HR0Q8xFYvSlRXMfYzWVBkszZ8EMFQmdwc6OU?PARTNER=WRITER) 

我是不管3721全部装上去了

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxSnIA08aKb5oxvASvkiIwL5eZBbJ24PZBE8sX7ihcwwFMGbcRK3wCchtZSsug5xREvu5vtZLP7FVlM-083vDk5?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhNnAwnFMJxrTSvRan2PoXhEMcCE3uuFj9GsyxbYAG0arGjo-yur0G7-FttPHoKnZVf8J7jrNvOks8THkJsReNqx?PARTNER=WRITER) 

装完软件，接下来的工作就要在LabVIEW下进行了：

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxdByVdnKD6_tCGf42nSl69TONk_l9kZrGkiwkq7DO6TsA8sMg0YQkvOQUILsrKBRo2MZgpv6sqWhjooKd73_mn?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhM1jZMKbePABwCFt07oTH2jQEUyxK-DTzUqEkW8-lq_c7WL_vr-kS_xjKC3fftRTx3mCMETIamiBE2WKmPok3kz?PARTNER=WRITER) 

让我们来调<font color="#ffffff">戏</font>试一下吧

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxjZihyANd5xa2cF3CaEQ7srMPc7Q00fnoxATNU_1DmzMIomrhe1h-SOJZUhdwus2vN4LzyQ6WqkyglZPWKqs7j?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxPnRWO9I4vqQAVgFuhuvTRscL-zL0DwnctiSattH6v5LgoOnh3JWOdQRrOD4ST9Oyi1hIRnqublPneYsXrsJeT?PARTNER=WRITER) 

一路下一步即可

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzdTCRiAwVQTLReo7AnBcteZKAcBycKw6tSHppjM1J8BhEznDbJC3vZp_ljFkn9Aghf9bYYxb0vbdYQY9Tb_zmP?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhNGxwQBybDtjhDolkPOuRROund4CfWkRGVIxQkwJ5G0wkZpFXYmz9W3sm6-_uf6N2Eos596yhuGHI6rYR0ZmzbH?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyXACCo5MBSlqTxtWLZfI3TbASXJwn101xyp6utUjQLzMP1JCdr39RseDX7ksMhfbx1cWheGVdtLOcOEwVITlQq?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhMj_K2d-6VOC_b75WGCDvyKx32W-3H0RAlWNAnRmNITU7uOP4d7srfDbcAz0Eo3gGnqyMh0p7sz3cy40OBNGkZD?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxltcV9Wbd5SlFYGODpTgIzaEYVcfoPVKD1rgfKBwlHWxMLePJhINmBJar__H-SsCufxD9Nos2qtC9yP30xBLid?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOoDEDmQzp4w9M5XkOitdx89RHapg3XB5psrLcAGdmuh6Y7ATSbMvlg0XVJ11JIskxAvusJilCoJhdAT6spOkbB?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyQmZUNSgIQLlgoP7HBnhJPmP8WQLVa4nsYTnqlfnDNMNlQglDmM0Js9tbxhbasy7mhsJvs0S-mWNMyOCn1Kb2N?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxOXqHEHD_-OIftYbsU5OXsd5-i-DGy3JZzbjlki90B2qE4woWZ0wxSe5dpeJLKzJy8Jwfm9bAZK-tYTJi2RWR8?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxWEf_twcS_ww6Xxdad3VwGl1vmzXR5mfgScp60xJ1lC4cgoR5nsyKC9vVZxpmN7iP1hDtYCy8v_TLcnUk1NA-b?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyeLgtNrBkqQ5soSLXlIXxIyZ1wkovF1fOioHVh2jyivxgoqF-DIP8hzXunrfo4YnsvOc-Qcfpdbx_MK_DXPf9r?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwZOfnJEc-VjaDMhNzDBQOP6H7bs0XuF-RCn9PC0NcgIuB50pc138DVn49uDjVxXzH9Z1P-URY09DZ6vVT66728?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOaGmhhrIJoQCNPe-9sVHAAifMrU3JDY8APz6dYk46lLUy7HE-hLKP2VHbx6FsQc5iJC-QsNJkYrmVrYa5p0D4m?PARTNER=WRITER) 

然后配置一下程序架构

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwX-GVEff8eBBaD_c2Nx8Q2nEcJbvkf1HKUvdXzDEPLWEgGgC3uPKbZynAzlXgqqjpRoVFwhwSx-rluairUjq5i?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPt3N5SVFsBtGX1F1sCCQMMopA27qmE21ZndE9Bi6sqWharyjg0TenBnx94P0p-qiuNOUndLmHqO3xE_VzJ0NOE?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpznx-EmcwBjR6Gz4X9WFNRuXRH_f8SXhk2TGccZEoCHEMbqkfizs7eGtj5jQ26v7JZk8lHjR4CU28CMxZ_H1pfj?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxEJ_Wd5P5aptJdCtvvT0QWkyRUB_hQi0MUc7UhGKeFWGyczs5aFDR_IDNvWC5xcE3qqubWFMZJG0mowiGzhSn9?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpytac4PwPhRwV7rja_nuwutyZ11M1hCdoywJfdC5H9RyICJObJa91UEcGP46bmIbOE01lkqsIiR9GSPX6GxaDGF?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyVaF5798WjH3G7kjEwfVgi6DEyyYiYQum3hi6adYS1EVFh9QAlZIoAZBK9G1aRItoal7SFpBbO_x0vqLq-n_qZ?PARTNER=WRITER) 点这个自动生成代码

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpyA1q9ARhdixqt47T640dXoMmBQp3pRiMsPKTjDRMLBtK208mC32HKsysn97ag4SAgPcxj94Z-gDXXk9RNBdfLo?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyv3SkmBZiFRdPp1ttZ3gaBSabQnzL2qoIzRzXZ5t8HHxFJXCdBo0rVu7zURnPNqlJryzY0206_bMtnKJcdUChS?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzq8Yzl3S8-HobFOOHDVjhRbpcCm3Kmkc0J9NgfoW_oMuiReEYFzLIDUGo4eaX2baeJymwqiJ1LWqtJhosmuKlY?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxiR4huo2b3b3-mOWFrKA1qHVrGEjkRtV_6rQJdpoQQZmd0WEBZj0a4rsLqXmBOeISDsOEDyufmwR-l3vJKgxnC?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwQG6_qXe3ms3Nf4Bc2YllPeN9KgaERwL7Dz2YfuGK-ux-yuStfolatSrJO58KzV0frUACJ_zyLw9CdeJaR3OW1?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxNhY39apcqhdvGgszVg7kvgm_Rrn0T0AvjbuEzduEgpgIr1WU7AIfP-v0NaneP3EAQd5oQHPMPknqu5zisNsV2?PARTNER=WRITER) 

大功告成！

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpy-B5KV1aSZcSkuyZoqiq6kFgF1YuyN1NOxzg2uql2sMfBvazQNhUUdpjiZhLPxB6EZUrmMAc1_0iaeutGGLza8?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpxQOKYYxmAt8Qb0f0O1-Rhjyz2ICTKqXpSRwQ_CK0UtJW4gq9zBOAlRSFfNigHlBvIEnS8IZIzKbQKXGAB9DPc8?PARTNER=WRITER) 

其实还MADAMADANANE!

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpzVWbCoIKZmqqzIDBtXFmhqkaL6k-evV393cl4d6NAhQesCNu2etsVJvdNBuK2q-Uj8RPbE-51IqWDcf7A6XPLv?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyYPvipnFM7ta4foMTJCFFJpQRTBBhC7j0YG4-3R7_7oiJ7FvgCF9zsw0otheDs_fssmv4jQipSns2NEVnROcb4?PARTNER=WRITER) 

恩 还有漫长的编译在等待着我们

[![image](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhOu1QOPMmfd2Aw_I4gJBCKT21bVg8j5QBgot6EGhqm7HBsjpvwQDygzE74YFlTbD4L1k8DA_Mj22MKELv0ULYSJ?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpyNn8i0rqiOIBhdct1HVxY3HNGwN2h0yyBXI8g3qW-3A529ZlDyWqgoqRzZ68rxkn7CFa-Yh4Ml8tChzlmUBkD5?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwrm-pqWTPukboyq28vem7oeStjvDEW_EkpMI2cIv7ezPCzAalp5wbcnjEis67Ug588_QAgDBwOO_olDXBH0YPD?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzhvm9UNOy5xnqdHbMSAZ6mhh4YLeU0VSu9nBzvZReyLNZpGxbBLLxdSrnWvpFnlhtQudzyNcjRWI4ufbMEmZfU?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpwJigp3YbDTVBfLdQdOSL4VrQ_88ElpY6uxDDV0QbTBOkE7xnG4XnMS-5uhzJDboUgOVtKBZsLKSUjeidx5IrLK?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhP3l4ZxZ09yAKNlPjI7FK3P0yKLKnlPNpEZNRMlNI-j9QTYEc-jXOnW35zGGMw46GA9KEQ52t_5dgikkDdn7Ljk?PARTNER=WRITER) 

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxWAmpiExA3HfqttkoMHvBFS35W8iySHMWODGKe1fqrQys6V5iC9OAYbtFWfwXXPgqjJlMfJSGlKnmPoqr7t5Rv?PARTNER=WRITER)](http://zdpe9q.bay.livefilestore.com/y1pAFYaglZOQhPTBj6yVC2fm2tEo4mUos8_8H4AdZgCkbQYkNi4ofd42SrlXTq9YKImDINq3BKkqCvXAxiT2HHeNVwSDjR68LHs?PARTNER=WRITER) 

正所谓不用FPGA不知道机器慢，各位可以吃饭去了，一般需要半个小时到几个小 时左右才能OK。

555 我果然被调<font color="#ffffff">戏</font>试了。。。

[![image](http://by2.storage.msn.com/y1p8NjIsGi7lpxIyMTwZMc3gsAIqd871mcOAYV3u3b8aiZIDFbqMQ90btapCGwciiaY-C3z-FIqtHl481FkcXkRZL-5TRpGZrxI?PARTNER=WRITER)](http://by2.storage.msn.com/y1p8NjIsGi7lpzOIyMNp8I5SeW9f86v9FgO-8ijfYMtbjLT3qTAf5FUoj9307YNWg4q93rg2e3v6hNnXuj4g7ujepwzQMDxRko6?PARTNER=WRITER) 

I will be back!我们下次继续。。。
</div>