---
layout: post
title: "统一单独的NAND安装工具发布"
categories: [news]
tags:
---
我创建了一个单独的NAND安装工具软件包，它支持A10(cubieboard1)和A20(cubieboard2)，无论内核版本。
要安装它，, 参照 [教程](http://cn.cubian.org/2013/08/09/cubian-update-is-available/) 添加GPG key并且正确配置apt软件源。
> apt-get update && apt-get install cubian-nandinstall

使用方法非常简单
> cubian-nandinstall

本NAND安装工具在多个环境下测试过，但未包含所有的环境。
如果遇到问题，欢迎到github上反馈bug。

# 注意
在NAND上运行的系统会读取 **uEnv.txt**（在SD卡上运行的系统会读取 **boot.scr**），如果安装后系统无法启动，请检查 **uEnv.txt** 中的内核启动参数是否正确。
尤其是root字段，在cubiebaord2 3.3.0内核上root为`/dev/nand3`，在cubieboard2 3.4.43内核上root应为`/dev/nandc`。
