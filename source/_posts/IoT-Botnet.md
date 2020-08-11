---
title: IoT Botnet
date: 2020-08-11 11:07:55
toc: true
thumbnail: 2020/08/11/IoT-Botnet/IoT_Botnet.png
categories:
- 学习
tags:
- 物联网
- 网络安全
- 僵尸网络
---

# Background

伴随着工业革命4.0，特别是物联网的发展，数字化转型正在全球范围内发生，并对交通、医疗保健、能源管理、自动化车辆等生活的各个领域带来了积极的影响。  

物联网等通信技术显著超越了对周围环境的传统感知，它赋予设备收集、量化和了解周围环境的能力。

<!--more-->  

物联网是计算机史上发展最快的领域之一，`Cisco`进行的一项调查[1]显示，物联网设备的数量每年都在上升，2020年可能会超过500亿台，互联网上连接的设备之间将交换44ZB的数据（1ZB等于1,000,000,000,000GB）。

一方面，物联网技术在赋能现实生活中的智能应用方面发挥着至关重要的作用，如智能家居、智能医疗等。但在另一方面，物联网的一些特性也带来了许多安全挑战。**而`Botnet`（僵尸网络）就是`IoT`网络面临的最大威胁。**

# Definitions

`IoT`：物联网

`Botnet`：“攻击者通过各种途径传播僵尸程序感染互联网上的大量主机，而被感染的主机将通过一个控制信道接收攻击者的指令，组成一个僵尸网络。之所以用僵尸网络这个名字，是为了更形象地让人们认识到这类危害的特点：众多的计算机在不知不觉中如同中国古老传说中的僵尸群一样被人驱赶和指挥着，成为被人利用的一种工具。”——百度百科

`DDos`：分布式拒绝服务攻击，攻击者控制`Botnet`向目标发动攻击，这种攻击可能是正常的服务请求，目的是耗尽目标的资源导致“拒绝向合法用户提供服务”。例如：大量地向某网站发送请求，导致真正想用此网站的用户无法得到服务。

# Features of IoT devices  

为什么`IoT`对`Botnet`非常有利，原因有以下几点：

+ `IoT`设备7*24运行，而不像PC会频繁开关机。
+ 许多`IoT`供应商为了提高产品的的易用性和用户体验的友好性，以及快速占领市场，往往忽视安全性。
+ 除非设备不正常工作，人们在安装好它之后就不再维护或忘记维护了。
+ `IoT`设备足以产生非常大的攻击流量，并不弱于桌面系统。

上述特性使得物联网吸引了很多恶意攻击者。

一个著名的例子是`Mirai`僵尸网络[2]，2016年8月它首次被白帽安全机构`MalwareMustDie`发现，`Mirai`的许多变体和模仿者已经成为了历史上最强大的`DDos`攻击的载体。

同年9月，计算机安全顾问`Brian Kreb`的网站受到620 Gbps流量的冲击——比使大多数网站崩溃所需的流量高出许多量级[3]。

几乎同时，一个使用`Mirai`的更大的`DDoS`攻击袭击了法国的网络主机和云服务提供商OVH.3，它的峰值达到了1.1Tbps[4]。

在`Mirai`的创造者公布源代码后，黑客提供了多达40万台设备同时连接的僵尸网络，并进行出租[5]。

# Mirai

`Mirai`是最著名的一个`IoT Botnet`，本节将对它展开描述。

## components

### Bot

`Bot`是用来感染物联网设备的恶意软件，并且具有传播能力，感染后能接收`master`的指令来发动攻击。

### C&C(command and control)

提供一个集中的管理接口给`master`，用来查看`Botnet`的状态或发动一次`DDos`。

### Loader

散播可执行文件到新的受害者（新的`Bot`）。

### Report Server

维护`Botnet`中所有的设备信息，新发现的可供感染的设备第一时间上报到`report server`。

## Key steps

![](Mirai.png)

1. 已经被感染了的`bot`会扫描附近的设备，尝试通过某些端口登录到这些潜在的受害者的控制台。因为物联网设备往往都使用默认的`password`，这个过程变得相当容易。
2. 当登录成功后，将受害者的信息发送给`Report server`，包括设备类型、型号、端口号以及`password`。
3. `Master`定期会去查看`Report server`，是否有新发现的潜在受害者。
4. 如果有潜在受害者，就发动感染指令。
5. `Loader`会根据设备的CPU架构、操作系统，选用合适的恶意程序发送给受害者并执行，执行后该受害者就成为了一个`Bot`。
6. 当`Botnet`达到一定的规模后，`Master`发动攻击指令。
7. `Bot`收到指令后就开展对目标主机的`DDos`攻击。

# Future work

最近关于`IoT Botnet`的论文几乎都是将机器学习/深度学习用于IoT网络的流量检测，以此来发现`Botnet`。

今后如果有时间和兴趣，或许可以在这方面做一些工作。

# References

[1] Cisco Internet of Things, 2015 (Accessed: 10-June 2019).

[2] Kolias C, Kambourakis G, Stavrou A, et al. DDoS in the IoT: Mirai and other botnets[J]. Computer, 2017, 50(7): 80-84.

[3] “KrebsOnSecurity Hit with Record DDoS,” blog, KrebsOnSecurity, 16 Sept. 2016; krebsonsecurity.com /2016/09/krebsonsecurity-hit -with-record-ddos.

[4] D. Goodin, “Record-Breaking DDoS Reportedly Delivered by >145K Hacked Cameras,” Ars Technica, 28 Sept. 2016; arstechnica.com/security /2016/09/botnet-of-145k-cameras -reportedly-deliver-internets-biggest -ddos-ever.

[5] C. Cimpanu, “You Can Now Rent a Mirai Botnet of 400,000 Bots,” BleepingComputer.com, 24 Nov. 2016; www.bleepingcomputer.com/news /security/you-can-now-rent-a-mirai -botnet-of-400-000-bots.