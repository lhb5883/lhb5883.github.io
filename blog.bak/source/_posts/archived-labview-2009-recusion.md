---
title: LabVIEW 2009递归研究
id: 23
categories:
  - Uncategorized
date: 2009-08-21 04:19:03
tags:
---

<div id="msgcns!866B8F96A2761BBE!1369" class="bvMsg">

**Part I ： Handson**

各位安装LabVIEW2009的同学请跟我做以下动作:

1:打开LabVIEW 2009.

[![image](https://f2gz7g.bay.livefilestore.com/y1mVYx9-iHIRHcVhl1R903uSWy0-7PkCqDKWTjNmCB171fHEVJhJmm79IjSw8KMzvYCuM6Z5NBkVimPJR-mpTTYeg90perGOqBtBghB04N9a5TZxdGEpKA43q7B8oH0ZeBmT9DvaqRKUNied1mU6jx0Hg/image_thumb 63232C87.png "image")](https://f2gz7g.bay.livefilestore.com/y1mJf781TsQY2lMDPJPSS-Ciy9j5BqCKwwYq4up4HegzWdSPRRoK9XmPUSm0MhcjjsGdO3yBFl5o2ZUoHcAEFlDD9Idvou3kEx52H_zGgNN4Qq5OZzivi1JsoCTqmPU_J_g-6lkWGxiRub0O8NdLW8Kxw/image2 7AFEC386.png) 

2:Ctrl+N

[![image](https://f2gz7g.bay.livefilestore.com/y1m0ogiAD6Jc2Cbxy3vpUAV6MrpE_K_Dabfar0aXUtgde7OEMLg1Ikyjmx3q6DM4dkzDU_ZVa6Vytc1aN8w4VtsYpBTtJfnyzax9NbFx2nJxlG1Xl3AxOMCDjiSzLGO49ZYdrJkMuRUh4NDF1juq0lLrw/image_thumb2 1A28A6A4.png "image")](https://f2gz7g.bay.livefilestore.com/y1mqUA4E2HIjdW9Gb3BZtx2IS9OvqufNm9ay5c3yoX7YyZtiExwtvNyKY6zO4IzSS5_hYD1H1mT82bnVU8GrzxlS_AzTvrzEsxkIBloXGJEeXVT03GQDPTy5-7VXeuYh0kU6fKN5Cf7WXnw8gIPYYITWQ/image8 2D5308B1.png) 

3:Ctrl+I,按下图配置

[![image](https://f2gz7g.bay.livefilestore.com/y1mWhcbcuZQz7gwaAOLMDXl0lxrADAEmDyvRlECQD82oaX6EZrXUYRrfHsVXGO5GeLIRwcnLZvKAYu-BD54k0csbzWE7BjJ2JoQWhEkENXymMMwr49aIlhjK48h_aaq6c4M4AbE7BrVuzcnTQsPSm0VWg/image_thumb4 796A50DA.png "image")](https://f2gz7g.bay.livefilestore.com/y1mTJsXhwFua2feHrRTHHidlP8UL_niDiOlgDLqXBogknVvLwNzcQLlDPnAj9Nd9eU-slt_5e4mpgKoMsZAIswHRF6d9eH2x-0u7mCNVuzKSd2K4VyE5RYrizBHaxPc6H5YnRiUspCSTyHZolbOHjRpMw/image12.png) 

4:Ctrl+E,选择程序框图,将图标拖到程序框图

[![image](https://f2gz7g.bay.livefilestore.com/y1mcDpF6XgX1ChPJouSMEIE3qw8z_IizPqK5nXIwFlwPTl6ctx5Sw4BOgOf6XBGnJ66dpW_iJwhD3q6fWGya3VDTf5jr2lAylB_2U88qUcEnbUvEFn6OVw03NftdN2c39p1nxqkamVlrhq0EH9BIeRwEQ/image_thumb6 708CFF2E.png "image")](https://f2gz7g.bay.livefilestore.com/y1mtg6ZXjelXoHmXA-xYApe6akbTKVKdtTBH_quMiSzKJndfpVbuYu7gLL-Sam_hY8rH9Icrm244_Qaw6dPLAScQj7ZbK8kxnE1jXgiKsLsGsYokS_LVM7UnagklPGUavrq6fYUsZCsgCP_K5VLYnHjqA/image16.png) 

5:Ctrl+R，然后稍等5分钟：

[![image](https://f2gz7g.bay.livefilestore.com/y1mTROt_oCMYrqvSPJ04o_93I-BcT6v-wjgCSDCnM2r6e99wb8w2-XPcgd7vl2bYbHxGH8iHmbm6lA-3n86m8LBhbvZdsfTObYKgeBqQVIeSACqPrq_vyUkRFBWol7Q7nG1F97-kUeP9s4nd3XNOmDj-g/image_thumb9.png "image")](https://f2gz7g.bay.livefilestore.com/y1m1yQuFE2PPchn6j3vH06VfbQjUhxybHx40VJLiaJvTh8Ug5ceO30uH-JkY3AW8fKT9SRvDTHf1WBG8f5DHqPiznrj_6UOcC3v6znY_IXbenCqaFABGdCOxuYloaJmHHVJIGZuG2CU3DqB4aC0LdfK4A/image23.png) 

恭喜你编写了第一个递归VI并且让他挂掉了。

** Part II ： Basic I**

好,我们来玩点实在的，先看看LabVIEW 的例程：

[![image](https://f2gz7g.bay.livefilestore.com/y1mm8KaiiUP0iV4jeZuGcGwDgHYgJPz8icKzsio12LxgM3wMzboQT03e5_5hSjVTQid9D00wpjamNWPQrSvLu67so_5EEkB_loAoqARIAbEZnlypl43vNLYAwX-ejCOE3_3RK3Ts2sFerIEN5_5dA-O0g/image_thumb2[1].png "image")](https://f2gz7g.bay.livefilestore.com/y1mvWEYPjzRXVMmpiuO4xUqrOXFHdNFe0v_y1tVO63ZJGZWgSxL7H_y9eUjrF71FHSZPW7h5_NkO6Ncsz_VXhrbaIIVDLG6mFk6J8DKUHii9Hagg4fAAsx6O6huAsx2nLXGUVP7Pr2DTY6CDSwbboXFaw/image6.png) 

![Demo Recursion](http://lhb5883.files.wordpress.com/2009/08/demorecursion5.png?w=300 "Demo Recursion") 

![Recursion](http://lhb5883.files.wordpress.com/2009/08/recursion5.png?w=300 "Recursion") 

在LabVIEW以前的版本只有类才能使用递归，不过现在已经比较成熟，普通的VI也可以递归了。

注意事项正如图中注释，我就不多废话。

**Part III ： Basic I**

为了更详细的演示递归，我们请出教科书里的经典例程汉诺塔。

首先附赠一个汉诺塔小游戏：

![image](http://lhb5883.files.wordpress.com/2009/08/image5b105d.png?w=300 "image") 

![hanoi tower](http://lhb5883.files.wordpress.com/2009/08/hanoitower5b55d.png?w=300 "hanoi tower") 

附赠小游戏汉诺塔下载：
  <div style="display:inline;float:none;margin:0;padding:0;"><div>[hanoi tower.7z](https://f2gz7g.bay.livefilestore.com/y1merIkYDIpelIzeY2GYQAQKA_dg4i8FbfdK8GaKiGoTUnlLXvcUNsixVC_kF4eKje1hkTltCHlbr3URvf3IbJRprYA5K2m3ioq8YP-5kcvqgqDIuJh4SpxX6Gu2Y6io3-54vvTfhsDJz7IiAT174ZuLg/hanoi.tower.7z)</div></div>（LabVIEW2009）  

  <div style="display:inline;float:none;margin:0;padding:0;"><pre style="background-color:#FFFFFF;white-space:pre-wrap;word-wrap:break-word;overflow:auto;"><span style="color:#000000;">#include </span><span style="color:#000000;">&lt;</span><span style="color:#000000;">stdio.h</span><span style="color:#000000;">&gt;</span><span style="color:#000000;">
</span><span style="color:#0000FF;">void</span><span style="color:#000000;"> hano(</span><span style="color:#0000FF;">int</span><span style="color:#000000;"> n,</span><span style="color:#0000FF;">char</span><span style="color:#000000;"> a,</span><span style="color:#0000FF;">char</span><span style="color:#000000;"> b,</span><span style="color:#0000FF;">char</span><span style="color:#000000;"> c)
&#123;
    </span><span style="color:#0000FF;">if</span><span style="color:#000000;">(n</span><span style="color:#000000;">==</span><span style="color:#800080;">1</span><span style="color:#000000;">) 
        printf(</span><span style="color:#800000;">&quot;</span><span style="color:#800000;">t将%d个盘片从%c移动到%cn</span><span style="color:#800000;">&quot;</span><span style="color:#000000;">,n,a,c);
    </span><span style="color:#0000FF;">else</span><span style="color:#000000;"> &#123;
        hano(n</span><span style="color:#000000;">-</span><span style="color:#800080;">1</span><span style="color:#000000;">,a,c,b);
        printf(</span><span style="color:#800000;">&quot;</span><span style="color:#800000;">t将第%d个盘片从%c移动到%cn</span><span style="color:#800000;">&quot;</span><span style="color:#000000;">,n,a,c);
        hano(n</span><span style="color:#000000;">-</span><span style="color:#800080;">1</span><span style="color:#000000;">,b,a,c);
    &#125;
&#125;
main()
&#123;
    </span><span style="color:#0000FF;">int</span><span style="color:#000000;"> n;
    printf(</span><span style="color:#800000;">&quot;</span><span style="color:#800000;">输入将要移动多少个盘子n:</span><span style="color:#800000;">&quot;</span><span style="color:#000000;">);
    scanf(</span><span style="color:#800000;">&quot;</span><span style="color:#800000;">%d</span><span style="color:#800000;">&quot;</span><span style="color:#000000;">,</span><span style="color:#000000;">&amp;</span><span style="color:#000000;">n);
    printf(</span><span style="color:#800000;">&quot;</span><span style="color:#800000;">递归结果：n</span><span style="color:#800000;">&quot;</span><span style="color:#000000;">);
    hano(n,</span><span style="color:#800000;">'</span><span style="color:#800000;">x</span><span style="color:#800000;">'</span><span style="color:#000000;">,</span><span style="color:#800000;">'</span><span style="color:#800000;">y</span><span style="color:#800000;">'</span><span style="color:#000000;">,</span><span style="color:#800000;">'</span><span style="color:#800000;">z</span><span style="color:#800000;">'</span><span style="color:#000000;">);
&#125; </span></pre></div>

然后我们来看看LabVIEW里面如何实现这个算法：

![auto hanoi tower](https://f2gz7g.bay.livefilestore.com/y1mprygHzelJggiWKEkuwsSFY4M5mNbiguBIY5D7W2O9OD5HWZEsrxZuv2G5dv0Xm0gKLPXG60Tm1TqkTvBTIdvpxXoYjKlQG6JepC8a0f9Q4pOsO7iWMu1mKv7QYUrD0oWkuV2bYUM7tVMWd4Y0Wtbnw/auto hanoi tower[2].png "auto hanoi tower") 

主程序调用算法，然后演示步骤。

![auto hanoi tower recursion](http://lhb5883.files.wordpress.com/2009/08/autohanoitowerrecursion5b25d.png?w=300 "auto hanoi tower recursion") 

递归调用算法。

![Quit Recursion](http://lhb5883.files.wordpress.com/2009/08/quitrecursion5b25d.png?w=300 "Quit Recursion") 

当然不要忘记设置退出递归的条件。

源代码下载

<div style="display:inline;float:none;margin:0;padding:0;"><div>[auto hanoi tower demo.7z](https://f2gz7g.bay.livefilestore.com/y1mzRAxsj5doJkMoW9WmdSPEQ3iq-X2OaTxJbPM4puKlPm79rh8T6O4U2h3pG8ZBzN8D6gzvsqrP-Sga8PVoRgSpxoLS5mprGxbuzJ3iO-ta5ZzyiZVb0tZ8eG5p_fnTbMme4M5-aBWVFHDog-XemQRKg/auto.hanoi.tower.demo.7z)</div></div>（LabVIEW2009）

**Part IV ： Advance I**

到底递归有什么用呢？我们来看一个实用一点的工具：VI图标提取器

![image](https://f2gz7g.bay.livefilestore.com/y1mthsEtKyirJ5UgEwqu1Pd_SHiauSyudG9LPT5gSFTKp2tj6WRPWmHr9vA2gFltVAbHriMUMAvKkkGATycCxvYG5XOLYLV3PVxcx6vxw_9xqv0B3IZsOa4bdHZnp9aCZerIg1khZ9lhQeoZnevNjoU-Q/image[13].png "image") 

主程序：

![output vi icon](http://lhb5883.files.wordpress.com/2009/08/outputviicon5b25d.png?w=203 "output vi icon") 

递归代码

![enum vi icon](http://lhb5883.files.wordpress.com/2009/08/enumviicon5b25d.png?w=300 "enum vi icon") 

源目录

![image](http://lhb5883.files.wordpress.com/2009/08/image5b195d37974858.png?w=300 "image") 

输出目录

![image](http://lhb5883.files.wordpress.com/2009/08/image5b165d72d9c6a2.png?w=300 "image") 

**Part V ： Advance II**

另外程序里附赠了一个利用LabVIEW自带的枚举函数写的同功能VI，大家可以看看，这个是可以枚举llb的。

![labview recusion path](http://lhb5883.files.wordpress.com/2009/08/labviewrecusionpath5b25d.png?w=300 "labview recusion path") 

<div style="display:inline;float:none;margin:0;padding:0;"><div>[Recursion VI  Icon.7z](https://f2gz7g.bay.livefilestore.com/y1mnRGuf_j3Gb5TpKVjOD5CxZ8UBELgZPqY3gZOVgWHl5DBflI0ZjbDuo1EUl-risW3uaQ7wgUlVRHJIDQ_ypyOhRQddP40jPnRG5uEJ1q_4sGMc7lSHn84388p379VGkZgLTFRvZ--1OjwUlAVXTMCtA/Recursion.VI..Icon.7z)</div></div>

最后总结一下递归要注意的事项：

<font color="#ff0000">**1：真的有必要用递归么？**</font>

<font color="#ff0000">**2：你的程序能否正常退出递归？**</font>

<font color="#ff0000">**3：递归的过程是无法直接调试的，有没有好的办法保证VI按照我们的预期执行？**</font>

如果这三个问题都能保证，恭喜你，你可以使用递归来提高你程序的效率了。
  </div>