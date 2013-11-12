---
layout: post
title: "Cubian r7（A10）和 r4（a20）发布"
categories: [news]
tags:
---
与[2013年11月8日](/2013/11/08/cubian-r6-for-a10-and-r3-for-a20-released)发布的版本对比，这次发布新增

* 在首次启动时自动扩大系统空间到全部SD卡
* 使用系统级别的自动挂载脚本(devmon)

# 提示
首次启动比平常所使用的时间要长一些。它需要重新生成SSH key，Ajenti 私有 key，并且重新调整分区以使用整个SD卡的空间。另外，它在首次启动时会自动重启一次使改动生效。

# Cubietruck
a20 r4可以在cubietrunck上工作。但是由于驱动改变，有线网卡暂时无法使用。
