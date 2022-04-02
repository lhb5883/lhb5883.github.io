---
title: 20200422-Network-Trouble-Shooting
date: 2020-04-22 15:18:29
tags: network
---

# 网络排故记录

## 前言

自疫情以来发现网络情况很不稳定，发现虚拟专网时有链接不上的情况。

 

## 网络拓扑

上海 WAN1 联通光纤固定IP+ WAN2 电信PPPOE 

通过飞塔防火墙软件定义网络宽带合一访问外网

飞塔防火墙在 WAN1 提供IPSEC隧道，WAN2提供SSL虚拟专网服务

西安 WAN1 联通专线固定IP+WAN2 电信PPPOE

通过飞塔防火墙软件定义网络宽带合一访问外网

飞塔防火墙在WAN1 拨号到IPSEC隧道以访问上海的内网资源

 

## 故障现象1

西安WAN1的IPSEC隧道失败，但可以用客户端SSL虚拟专网访问。

### 故障确认：

使用TraceRT发现上海WAN1的固定IP无法Ping通，

### 故障原因：

是联通网络问题。

 

## 故障现象2

IPSEC隧道正常，使用客户端SSL虚拟专网无法访问。客户端在忽略证书错误后就无法再连接上。

### 故障确认：

使用Web界面可以用账号密码正常登录，确认网络通讯正常，账号密码正常。

更换机器也可以正常连接。卸载当前版本飞塔客户端重装无效，但更换版本后可以正常工作，如从5.6升级到6.2，或者从6.2降级到5.6都可以。

### 故障原因：

怀疑是注册表或者配置文件出错。

 

## 故障现象3

IPSEC隧道失败，客户端拨SSL虚拟专网失败。

### 故障确认：

Web界面无法打开，确认网络不通。

### 故障原因：

上海端电信PPPOE拨号失败。

 

## 故障现象4

IPSEC连接失败，客户端SSL虚拟专网随机性断开。

### 故障确认：

飞塔CPU占用100%，经过测试，只要下载速度超过10MB/s，防火墙就没有响应。查询手册，UDP包最大速率1.5Gbps，防火墙策略 5000 SSL虚拟专网吞吐量 30Mbps，IPS吞吐量只有200Mbps也就是20MB/s但实际上测试只要到10MB/s的下载速度，CPU就已经100%了。

### 故障原因：

防火墙IPS性能不足

 

 查了一下，防火墙IPS指的是防火墙的处理能力

Most vendors talk of firewall throughput even when they are advertising UTMs (Unified Threat Management Systems). There’s a fundamental difference between a firewall and a UTM. A firewall merely does stateful inspection of the traffic whereas a UTM proactively stops attacks even on allowed ports because it contains the all important IPS (Intrusion Prevention System). This means that even if traffic is allowed to certain services, that traffic is continuously examined to detect malicious attacks. In other words, the IPS stops hacker attacks even on open ports.

 

