---
layout: post
title: "扩大Cubian根文件系统分区工具"
categories: [news]
tags:
---
根文件系统分区在Cubian上默认是1GB 减去 100MB。要扩大这个分区以获得更多空间。[这里](http://askubuntu.com/questions/24027/how-to-resize-a-ext4-root-partition-at-runtime) 有个小教程。  
为方便使用，我基于这个教程写了一个工具叫 `cubian-resizefs`。

# 安装

首先, [导入 GPG key 并添加 apt 源](http://cn.cubian.org/2013/08/09/cubian-update-is-available)。

然后， 
> apt-get update && apt-get install cubian-resizefs

# 使用方法

> cubian-resizefs 设备 比例值

**比例值** 在1和100之间, 如果没有提供 **比例值**，则使用整个SD卡。
举例来说，如果比例值是50，代表使用SD卡一半的空间。如果是75，则代表使用全部空间的3/4

> cubian-resizefs /dev/mmcblk0

# 注意

我们内部使用了 `fdisk` 修改分区表, 这总是有风险的。因此会自动备份旧分区表，万一有问题发生，
你可以通过恢复分区表解决。

> dd if=PATH_TO_MBR_BAK of=/dev/MMC_DEVICE bs=1 count=64 skip=446 seek=446
