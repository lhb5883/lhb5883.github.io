---
title: 20190103-labview-2018-call-python-return-error-1671
date: 2019-01-03 14:12:54

---

# LabVIEW调用Python返回数组时报错1671

最近在测试用LabVIEW和Python实现算法时的可替换性,正好LabVIEW 2018可以调用Python代码就方便了不少,可以直接替换比对.但是发现调Python时返回单个值的时候正常,返回一个数组时报错.

Error 1671 occurred at Python Node in PythonNode_PyIntegral.vi

Possible reason(s):

LabVIEW: (Hex 0x687) There was an error in executing the specified function.

Python returned the following error: <class 'SystemError'>

..\Objects\listobject.c:186: bad argument to internal function

 

查了一下LabVIEW帮助,返回值应该是支持数组才对的啊?

仔细研究了一下发现了一条附注:

Calling Conventions

This node converts integers and strings to the corresponding data types in Python, converts arrays to lists, and converts clusters to tuples.

输入参数的时候有类型转换,那么是不是返回值的时候没有转换?

在python里打印了一下返回值的type,是np.ndarray,于是手动转换成list,果然就可以正常工作了.