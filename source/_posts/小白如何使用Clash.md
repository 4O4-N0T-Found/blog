---
title: 小白如何使用Clash
date: 2020-03-02 12:45:29
toc: true
thumbnail: 2020/03/02/小白如何使用Clash/clash.png
categories:
- 教程
tags:
- 梯子
- clash
---
你有没有遇到过这些情况：  
+ 给服务器装环境的时候，例如装Java，需要到oracle官网上去下载jdk，那速度简直不谈。  
+ 有时候查资料需要用到Google。  
+ 想上twitter看看特朗普的最新发言：“没有人比我更懂***”。 
 
**这都2020年了，是时候掌握一种上网的新姿势了。**  
<!--more-->
# Why Clash
Clash是一款比较先进的代理软件，可能你以前用过一些VPN或者ss、ssr。**Clash比它们都更加强大！**  
它的优点在于：
* 不同于VPN，VPN需要一个与服务器建立连接的过程。但Clash不需要，它的流量更加不容易被发现。
* Clash可以配置出站规则，**访问国内的服务时会选择直连，访问国外的服务时它会自动选择代理。**
* **所以你可以24h打开Clash**，它不会影响你访问国内服务的速度。相反，如果你使用VPN，访问国内的服务时就会变得很慢。

# 准备材料
* **确保在“上网”之前，你已经形成了自己的三观。**  

# 购买节点
最近发现了一个比较好的“机场”，这几天在进行5折促销。  
首先注册[布丁网络加速](https://pud.life/aff/8ntE)。  
截止今天（2020-03-02），有这些价位的节点：  
![](流量商店.png)  
我推荐购买年付88元的套餐，每个月128G流量应该是足够用的。再加上现在限时5折，44RMB就可以解决问题。  
接下来就到**充值中心**进行充值，然后在**流量商店**中购买套餐。购买成功之后，在**用户面板**就能看到流量信息了。  
![](流量信息.png)  
# 下载Clash
Clash是全平台支持的：macOS、Windows、Android、iOS。
## macOS
这里是ClashX的GitHub链接：[ClashX](https://github.com/yichengchen/clashX/releases)  
![](clashx.png)  
**下载ClashX.dmg，并安装。**
## Windows
这里是Clash for Windows的GitHub链接：[Clash for Windows](https://github.com/Fndroid/clash_for_windows_pkg/releases)  
![](clashforwin.png)  
**下载exe文件，并安装。**
## Android
这里是Clash for Android的GitHub链接：[Clash for Android](https://github.com/Kr328/ClashForAndroid/releases)  
![](clashforandroid.png)  
**下载apk文件，并安装。**  
## iOS
iOS设备需要用国外的AppleID登录App Store，下载Quantumult X。它是一个付费软件，大概是3～5美元。
# 配置Clash
首先到布丁加速器的**用户面板**复制节点链接。
![](节点链接.png)  
**注意：先选择Clash，然后再复制链接。**
## macOS
### 添加节点
打开刚刚安装好的ClashX。点击**配置——托管配置——管理。**  
![](mac配置1.png)  
然后点击添加，把刚刚复制的链接填进第一行，第二行可以随便填。
![](mac配置2.png)  
添加完成后点击确定。  
### 系统代理和出站模式
接下来还有最后两步：
* 将Clash的出站模式改为规则判断。  
* 勾选“设置为系统代理”。  
 
![](mac配置3.png)  
**大功告成！开始上网吧！**
## Windows
### 添加节点
打开刚刚安装好的Clash。
点击Profiles，把把刚刚复制的链接填进去，然后点Download。  
![](win配置1.png)  
### 出站模式
点击Proxies，选择Rule。
![](win配置2.png)  
### 系统代理
点击General，打开System proxy。  
![](win配置3.png)  
**大功告成！开始上网吧！**
## Android
### 添加节点
打开刚刚安装好的Clash，点击**配置——新配置——从URL导入。**
![](安卓配置1.png)
名称随便填，把刚刚复制的节点链接填入URL，最后一行自动更新不用管。然后点右上角保存。
![](安卓配置2.png)
勾选刚刚添加的配置文件。然后回到主页，点击启动Clash。  
### 出站模式
在主页点击**代理——右上角——模式**，选择“规则”。  
![](安卓配置3.png)  
**大功告成！开始上网吧！**  
## iOS
### 复制节点链接
![](iOS配置1.png)  
注意这里要选择Quantumult X。  
### 添加节点
打开Quantumult X，点击右下角的图标——节点——引用（订阅）。  
填写刚刚复制的节点链接，然后保存。
### 出站模式  
然后在最下方选择“其他设置”，勾选“规则分流”。  
**大功告成！开始上网吧！**    
# 结语
Clash其实还有很多高级功能，如果你喜欢折腾。可以去[GitHub](https://github.com/Dreamacro/clash)上看看它的其他功能，或者给一个star。  
Clash可以实现强大的规则分流，比如：访问美国的服务就使用美国的节点，访问英国的服务就使用英国的节点，你可以同时访问多个服务，Clash会自动将这些流量发往不同的节点。  
**最后，希望同学们在上网的过程中，擦亮双眼，善于辨别，好好学习，天天向上！**  
**请遵守相关法律，本教程仅供科研学习使用。**