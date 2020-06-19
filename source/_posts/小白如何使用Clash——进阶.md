---
title: 小白如何使用Clash——进阶
date: 2020-03-21 15:24:06
toc: true
thumbnail: 2020/03/21/小白如何使用Clash——进阶/subconverter.png
categories:
- 教程
tags:
- 梯子
- clash
---
使用了一段时间的Clash之后，有没有遇到这些问题：
+ 你可能想使用速度普遍更快的香港节点，但机场提供的默认配置文件使用的是新加坡、俄罗斯......  
+ 默认只能固定使用一个节点，没法手动切换。
+ 某些网站的访问速度不理想。
+ Youtube等网站会识别你的位置为节点所在的国家，但并不如你的意愿。  
**是时候展现一下Clash的强大之处了！**
<!--more-->
# Clash的强大之处
Clash最大的好处就是能配置出站规则，可以根据规则来把不同的流量分发到不同的节点。  
**听不懂？那就说简单一点：**  
不同于VPN，打开VPN虽然可以访问国外的网站，但使用国内的服务就会很慢。  
但Clash可以让网络按你想走的路径走，比如你想**同时**用国内的微信、用美国的节点看Youtube、英国的节点看BBC、香港的节点......。  
Clash可以保证它们的速度都很快！  
**但是配置Clash也不是一件容易的事情，本着开源的精神，博主开源了一个接口，可以让小白3步实现Clash的进阶！**  
# 第一步
**把机场提供给你的节点链接复制下来。**  
![](节点链接.png)
# 第二步
**把链接进行URL编码。**  
网上有很多在线的URL编码工具，例如[站长工具](http://tool.chinaz.com/tools/urlencode.aspx)。  
把第一步中复制好的链接填进去，然后点击编码。
![](URL.png)
**最后把编码后的链接复制下来。**。
# 第三步
这里就要使用到博主开源的接口了。  
`http://subconverter.songshuwei.xyz/sub?target=clash&url=`
**把第二步中的链接，拼接在这个链接的后面。然后把整个链接全部复制下来。**  
# 验收成果
最后，把第三步中的链接作为节点链接，添加到你的Clash当中。  
如果你忘记怎么添加了，可以参考我的上一篇博客——[小白如何使用Clash](https://songshuwei.xyz/2020/03/02/小白如何使用Clash/)，`5 配置Clash`中详细讲了怎么添加配置文件。  
**添加完成之后，就能看到这样的效果👇**  
![](clash.png)
**这样Clash就能自动帮你选择最优的节点去访问不同的网站啦！Enjoy！**  
# 不止于小白  
这个接口使用的是GitHub上的一个开源项目：[subconverter](https://github.com/tindy2013/subconverter)。  
它不仅支持Clash，还有很多：ClashR、Quantumult、Quantumult X、SS、SSR、V2Ray等等等等。  
## 接口说明  
### 调用地址
调用地址：  
`http://127.0.0.1:25500/sub?target=%TARGET%&url=%URL%&config=%CONFIG%`  
当然，你可以使用我的接口：  
`http://subconverter.songshuwei.xyz/sub?target=%TARGET%&url=%URL%&config=%CONFIG%`    
### 调用说明
![](调用说明.png)  
**你也可以查看它官方的[中文文档](https://github.com/tindy2013/subconverter/blob/master/README-cn.md)，有更加详细的说明。**  
# 结语  
配置好出站规则之后，这才算是使用上了真正的Clash。  
Enjoy！

