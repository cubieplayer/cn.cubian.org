---
layout: post
title: "A20 NAND安装常见问题解决"
categories: [news]
tags:
---
Cubian-nandinstall 可以让你非常简单的把根文件系统从SD卡迁移到NAND上。但是有时候即使你执行安装脚本并没有出错，系统仍然有可能启不起来。

#boot0 和 boot1

其中一个已知的原因是设备上的 boot0 和 boot1 代码, boot0 和 boot1 位于 NAND 上的一个特殊区域，据我所知，只有 livesuit 能够访问。它们可能并不是为了运行Linux而设计的，比如，Cubieboard 就会在出厂的时候在NAND上安装 Android系统。

要解决这个问题也很简单，你只需要首先使用 livesuit 刷入 [lubuntu](http://cubieboard.org/download/)，然后再使用cubian-nandinstall 即可。

**请注意，每次你都需要重复这个步骤，如果你在NAND里重新刷入了Android系统。**

#uEnv.txt 里的 root 参数
另一个常见的问题是 uEnv.txt 里设置的 root 参数不对。 nand安装脚本会设置 `root=/dev/nandb`。这是没有问题，如果你使用的是Cubian的内核。 如果你用的是patwood的内核，那么它应该是 `/dev/nand2`。 这里的设备名称取决于内核配置 **CONFIG_SUNXI_NAND_COMPAT_DEV**.

如果nand安装仍然有问题，请留言。
