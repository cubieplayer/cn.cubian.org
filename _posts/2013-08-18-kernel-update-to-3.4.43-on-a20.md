---
layout: post
title: "Cubieboard2(A20)内核更新到3.4.43"
categories: News
tags:
---
cubieboard2(A20)的Cubian已经更新内核，从3.3.0升级到3.4.43。
好消息是 **gpio_sunxi** 和 **mali** 已经可以在cubieboard2上工作了。
要在开机后自动加载驱动，反注释 **/etc/modules** 中相应的行。
另外，Ralink无线驱动已经编译进内核，但尚未进行测试，驱动的名字叫`rt5370sta`。

你需要更新 [cubian-update](http://cn.cubian.org/2013/08/09/cubian-update-is-available/) 到最新版(1.0-5)。要更新，执行
> apt-get update && apt-get install cubian-update

要更新内核，请执行
> cubian-update

如果遇到问题，请开启罗嗦模式以得到更多信息
> cubian-update -v

如果更新以后需要降级内核，执行
> cubian-update --revert-firmware

如果你使用新内核，因为NAND驱动的改变，旧的NAND安装工具无法正常工作。
请使用新的[统一的NAND安装工具](http://cn.cubian.org/2013/08/18/universal-and-separate-nandinstaller-is-released)取代

欢迎使用新内核，如果有问题欢迎到Github上反馈。
