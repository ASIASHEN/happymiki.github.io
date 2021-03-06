---
layout:     post
title:      OSI七层参考模型
subtitle:   网络分层参考模型
date:       2017-09-11
author:     Mlin
header-img: img/post-bg-OSI.jpg
catalog: true
tags:
    - OSI
    - 通信协议
---


> 本文首次发布于 [Mlin Blog](http://happymiki.top)、[简书](http://www.jianshu.com/u/3f05018752b8)，作者 [@木林(Mlin)](http://github.com/happymiki) ,转载请保留原文链接。

> 上一篇文章 [《Linux基础命令》](https://happymiki.github.io/2017/09/03/Linux常用命令/)。


# 前言
开放系统互连参考模型 (Open System Interconnect 简称OSI）是国际标准化组织(ISO)和国际电报电话咨询委员会(CCITT)联合制定的开放系统互连参考模型，为开放式互连信息系统提供了一种功能结构的框架。它从低到高分别是：物理层、数据链路层、网络层、传输层、会话层、表示层和应用层。
# 目录

# 正文

## 一、协议
### 1.协议的必要性
协议如同人与人对话

	“协议”——语言
	“通信”——聊天
	“数据”——内容

![](http://upload-images.jianshu.io/upload_images/6757403-ab7e84394404ed9c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2.数据通信协议

- 计算机网络传输数据过程中，事先决定数据的格式和传输的规定或“约定”，且网络设备遵循这一系列“约定”对数据进行处理——协议。

- 协议使不同厂商的设备、不同CPU、不同操作系统之间，只要遵循相同的协议就能实现通信。



### 3.不同体系的网络协议


<table>
        <tr>
            <th>网络体系结构</th>
            <th>协议</th>
            <th>主要用途</th>
        </tr>
        <tr>
            <th>TCP/IP</th>
            <th>IP, ICMP, TCP, UDP, HTTP, TELNET, SNMP, SMTP…</th>
            <th>互联网、局域网</th>
        </tr>
        <tr>
            <th>IPX/SPX(NetWare)</th>
            <th>IPX, SPX, NPC…</th>
            <th>个人电脑局域网</th>
        </tr>
        <tr>
            <th>AppleTalk</th>
            <th>DDP, RTMP, AEP, ATP, ZIP…</th>
            <th>苹果公司现有产品的局域网</th>
        </tr>
        <tr>
            <th>DECnet</th>
            <th>DPR,NSP,SCP…</th>
            <th>前DEC小型机</th>
        </tr>
        <tr>
            <th>OSI</th>
            <th>FTAM, MOTIS, VT, CMIS/CMIP, CLNP, CONP…</th>
            <th>-</th>
        </tr>
        <tr>
            <th>XNS</th>
            <th>IDP, SPP, PEP…</th>
            <th>施乐公司网络</th>
        </tr>
</table>

### 4.协议的标准化
- ISO:国际标准化组织
	- ( International Organization for Standardization )
- OSI:开放系统互联
	- ( open system interconnection )
- 20世纪70年代后期，ISO推出了OSI参考模型，希望不同供应商的网络之间能够相互协同工作。

## 二、OSI七层参考模型
### 1.OSI参考模型

![](http://upload-images.jianshu.io/upload_images/6757403-017d0d976d75b011.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2.应用层（高）

| 层 | 分层名称    |  功能                   |  相关规范                  | 各层功能概览|
| 7  | 应用层     |  提供应用程序间的通信      |  Telnet、FTP、HTTP…       | 人机交互界面|
| 6  | 表示层     |  处理数据格式、数据加密等  |  ASCII、JPEG...           | |
| 5  | 会话层     |  建立、维护和管理会话...   |  操作系统、应用程序访问调度  | 隔离不同的应用程序|



### 3.数据流层

| 层 | 分层名称    | 功能                                      |  相关规范               | 各层功能概览|
| 4  | 传输层     |  建立主机端到端的连接，区分不同的上层应用，校验 |  TCP、UDP、SPX         | |
| 3  | 网络层     |  逻辑寻址&路由选择                          |  IP、IPX...            | |
| 2  | 数据链路层 |  介质访问，组合成帧，差错校验                 |  802.3/802.2，HDLC...  | |
| 1  | 物理层     |  比特流传输                                |  V0.35                 | |



### 4.物理层

- 定义：
	- 介质类型
	- 连接类型
	- 信令类型

![](http://upload-images.jianshu.io/upload_images/6757403-2a6387feb3e254d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 5.物理层设备：集线器（HUB）

- 所有的设备在同一个冲突域中
- 所有的设备在同一个广播域中
- 设备共享相同的带宽
- 节点越多意味着冲突越多
- CSMA/CD被用来避免冲突

![](http://upload-images.jianshu.io/upload_images/6757403-0b1f44bc816ed91e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 6.CSMA/CD

![](http://upload-images.jianshu.io/upload_images/6757403-796dcaa7ff587f14.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 先听后发，边发边听，冲突停发，随机延迟后再发。

### 7.单工&双工 工作模式
![](http://upload-images.jianshu.io/upload_images/6757403-3eaa06b3bc596c30.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 8.数据链路层功能

- 源和目标的物理地址
- 与帧关联的高层协议 (Service Access Point)
- 帧顺序
- 数据流控制

![](http://upload-images.jianshu.io/upload_images/6757403-31e4229933f55810.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 9.数据链路层报文

![](http://upload-images.jianshu.io/upload_images/6757403-620f7887918887d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

参考资料：[链路层常见报文格式及长度](http://blog.csdn.net/rider628/article/details/7557646)

### 10.数据链路层设备：交换机
- 接口分割冲突域
- 所有设备在同一个广播域中

![](http://upload-images.jianshu.io/upload_images/6757403-d854c7866018a87c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 11.网络层功能

- 定义与指定协议相关联的源和目标逻辑地址
- 定义通过网络的路径
- 多链路连接

![](http://upload-images.jianshu.io/upload_images/6757403-0a01be6a9abf9536.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 12.网络层报文

![](http://upload-images.jianshu.io/upload_images/6757403-dab53ce6274ccf23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

参考资料：[网络层——IP报文头介绍](http://www.cnblogs.com/xiehy/archive/2013/07/02/3166953.html)

### 13.网络层设备：路由器

- 广播信息控制
- 多点发送信息控制
- 路径优化
- 流量管制
- 逻辑寻址
- 提供WAN连接

![](http://upload-images.jianshu.io/upload_images/6757403-dc89cfe1127f7248.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 14.传输层功能

- 区分不同的上层应用
- 建立应用间的端到端连接
- 定义流量控制 
- 为数据传输提供可靠或不可靠的连接服务

![](http://upload-images.jianshu.io/upload_images/6757403-62b03583cedd6ee7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 15.OSI参考模型的优点

- 促进标准化工作；
- 各层间结构上相互独立，把网络操作分成低复杂性单元；
- 灵活性好，某一层变化不会影响到其他层；
- 各层间通过一个“接口”实现上下层通信；
- 易于实现和维护；
- 便于学习；

### 16.OSI参考模型的缺陷
- 许多功能在多个层次重复，有冗余感（如流控，差错控制等）
- 各层功能分配不均匀（链路、网络层任务重，会话层任务轻）
- 功能和服务定义复杂，很难产品化（实际应用中几乎没有完全按OSI七层模型设计的产品）

## 三、OSI参考模型通信过程
### 1.通信过程类比

![](http://upload-images.jianshu.io/upload_images/6757403-912cf00d36e895b3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2.封装与解封装
- 封装（encapsulate/encapsulation）：数据要通过网络进行传输，要从高层一层一层的向下传送，如果一个主机要传送数据到别的主机，先把数据装到一个特殊协议报头中，这个过程叫——封装。
- 封装分为：切片和加控制信息。
- 解封装：封装的逆向过程。

### 3.数据封装过程
![](http://upload-images.jianshu.io/upload_images/6757403-f1dad8a80bf7cffb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 4.数据解封装过程
![](http://upload-images.jianshu.io/upload_images/6757403-f1dad8a80bf7cffb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 5.七层通信
![](http://upload-images.jianshu.io/upload_images/6757403-ebf4f41f71607a88.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](http://upload-images.jianshu.io/upload_images/6757403-f63efbacdb7083a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 6.PDU

- PDU（Protocol Data Unit)：每一层使用自己层的协议和别的系统的对应层相互通信，协议层的协议在对等层之间交换的信息叫协议数据单元。
- 应用（上）层：message  消息
- Transport layer：segment  数据段
- Network layer：packet  数据包
- Data-link layer：frame  数据帧
- Physical layer：bit  比特流

### 7.设备对比
![](http://upload-images.jianshu.io/upload_images/6757403-74c99053d2d90897.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 结语
- 掌握OSI层次模型各层的主要功能；
- 描述数据在源和目标设备间的传送过程；
- 清楚集线器、交换机和路由器在网络中担当的角色和功能；
- 懂得在什么情况下该用什么样的设备；
