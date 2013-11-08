---
layout: post
title: "Cubian r6（A10）和 r3（A20）发布"
categories: [news]
tags:
---
Cubian现在是cubieboard上一个锤炼过的系统，看一下[问题跟踪系统](https://github.com/cubieplayer/Cubian/issues)吧。 **干净** 和 **简单** 是它的背后的哲学. 

这次发布包含了以下特性，希望你能喜欢:

* 内核更新到当前的最新版本3.4.67+
* 更新了U-Boot，加快启动速度
* 更多的WIFI模块支持
* 预安装Web控制面板Ajenti
* 预安装[udevil](http://ignorantguru.github.io/udevil/)

# 演示
系统闲置时的负载看起来不错。
![cubian系统负载屏幕截图](http://cubieplayer.github.io/static_files/images/cubian_r6_loadaverage.png)

[Ajenti](http://ajenti.org/) Web控制台。登录用户名和密码分别是 **root**:**admin**.  
**注意**：你或许看到了闲置空间只有26MB，我推荐你使用[cubian-resizefs](http://cubian.org/2013/08/12/enlarge-cubian-rootfs-partition/)来扩大空间。
![cubian上的ajenti屏幕截图](http://cubieplayer.github.io/static_files/images/cubian-ajenti.png)

# 最后
Cubian很块就会有一个桌面版，我正努力早日完成它。我可以告诉你的是，它真的很棒。
