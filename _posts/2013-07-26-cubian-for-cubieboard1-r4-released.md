---
layout: post
title: "Cubian r4 cubieboard1版发布"
categories: News
tags:
---
r4 有如下改变:

* **性能优化**  
  * 减少系统日志读写
> 发行版的默认配置里，系统日志一般配置全面。这适合于服务器或者多用户的系统。然而，在单用户的系统下，频繁写日志会降低系统的性能。减少日志读写对提高系统性能和延长内存寿命是有好处的。
  * 对CPU频率进行了优化
> 最低CPU频率设为300MHz
> 最高CPU频率设为1.2GHz
  * 禁用了ext4文件系统的日志功能

* **普通用户现在可以看到（不可执行）那些需要root权限的命令**  
  比如 reboot, shutdown 等.

* **默认安装了一些实用工具**  
  fex2bin,bin2fex 安装到 /usr/bin. nand-part, nand-part2 安装到 /usr/sbin.  
> nand-part与nand-part2是可以对cubieboard上的nand分区的工具  
> 使用nand-part的例子: nand-part /dev/nand "linux 0"  
> 使用nand-part2的例子: nand-part2 /dev/nand 16 "boot 2048" "linux 0"  
> nand-part和nand-part2的不同之处在于nand-part2支持对整个nand进行分区，nand-part则不会改变第一个分区。nand-part2 的作者是 [patrickhwood](https://github.com/patrickhwood)

* **移除了交换分区**  
  没有必要把它为内置的特性。如果真的需要交换内存空间，你可以使用一个叫`gparted`的工具。

* **内核重新编译进了一些新特性**  
