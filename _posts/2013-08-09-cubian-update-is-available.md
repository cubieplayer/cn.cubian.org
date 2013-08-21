---
layout: post
title: "Cubian 更新工具发布"
categories: [news]
tags:
---
cubian-update 是一个可以保持内核和模块更新的工具

第一步. 添加 GPG key (需要 root 权限)
> wget -O - http://packages.cubian.org/cubian.gpg.key | apt-key add -

第二步. 添加 apt 源, 添加此行到 `/etc/apt/sources.list`
> deb http://packages.cubian.org/ wheezy main

第三步. 安装
> apt-get update && apt-get install cubian-update

然后执行 `cubian-update` 或者 `cubian-update -h` 获取帮助.

# 屏幕截图 
![cubian-update 截图](http://cubieplayer.github.io/static_files/images/cubian-update.png)
