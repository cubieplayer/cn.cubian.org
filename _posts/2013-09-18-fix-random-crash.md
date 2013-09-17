---
layout: post
title: "修复随机 crash 的问题"
categories: [news]
tags:
---

我收到一些关于 Cubian 随机 crash 的反馈。看起来这个问题根 CPU 超频有关。谢谢[346L3](https://github.com/cubieplayer/Cubian/issues/109)。

Cubian把最大CPU频率设置为 1.2GHz 以获得更好的性能。但是副作用是 CPU 有时候会启动保护，导致内核崩溃。方糖科技的 **Benn Huang** 建议我把这个值设为1008Mhz。  

# 解决方案

* 手动 
  编辑 `etc/init.d/cubian-ondemandcpufreq`，找到
  > echo -n 1200000 > /sys/devices/system/cpu/${cpu}/cpufreq/scaling_max_freq  

  替换为  
  > echo -n 1008000 > /sys/devices/system/cpu/${cpu}/cpufreq/scaling_max_freq

* 自动 
  这需要你更新 cubian-update 到当前的最新版 v1.1.1，  
  >  apt-get update   
  >  apt-get install cubian-update  

  然后运行 `cubian-update` 应该就能解决问题了。这个更新同时也解决了A10上的 [SATA驱动问题](https://github.com/cubieplayer/Cubian/issues/100)。
