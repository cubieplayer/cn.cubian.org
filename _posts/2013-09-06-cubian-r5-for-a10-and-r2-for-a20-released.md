---
layout: post
title: "Cubian r5（A10）和 r2（A20） 发布"
categories: [news]
tags:
---
这个版本修复了一些缺陷和一个安全问题。

* SATA 驱动内建到了内核
* 启用了 SPI,webcam,NFS,wireless 等模块。
* 修复了一处启动时[挂起](https://github.com/cubieplayer/Cubian/issues/36)的问题。
* 第一次启动时生成SSH key。
* 移除了Nand安装文件夹。 请使用[安装工具](http://cn.cubian.org/2013/08/18/universal-and-separate-nandinstaller-is-released)代替。
* 集成 [cubian-update](http://localhost:4000/2013/08/09/cubian-update-is-available)

# 提示

为了减少安装时间，镜像大小设置为1GB减去100MB。你可能需要扩大rootfs以使用更多空间。我推荐使用 [cubian-resizefs](http://cn.cubian.org/2013/08/12/enlarge-cubian-rootfs-partition).因为已经在这个版本里包含了cubian的软件源，所以你现在不需要像教程说的那样去添加了。

举例来说，如果你有一个 8GB 的 SD 卡, 想要使用一半的空间。

> cubian-resizefs /dev/mmcblk0 50

Cubian 现在已经相当稳定了，我会有更多的时间花在教程上。  

# 最后
我已经收到了一些捐助，谢谢你们。
