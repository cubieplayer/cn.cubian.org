---
layout: post
title: "Cubian for cubieboard1 r4 released"
categories: News
tags:
---
r4 has a few changes:

* **Performance enhanced**  
  * Reduced system logging activity
> In a default distro install, system logging is often configured fully, suitable for a server or multi-user system. However, on a single-user system the constant writing the many system log files will result in reduced interactive system performance, and reducing logging activity will be beneficial for performance as well as the lifetime of the flash memory.
  * CPU frequency is optimized
> The minimal cpu frequency sets to 300MHz
> The maximal cpu frequency sets to 1.2GHz
  * ext4 filesystem journaling is disabled

* **The normal user now can see(not execute) the commands which requires root privileges**  
  Such as reboot, shutdown etc.

* **Various utilities is installed by default**  
  fex2bin,bin2fex is installed to /usr/bin. nand-part, nand-part2 is installed to /usr/sbin.  
> nand-part and nand-part2 are programs which supports repartition the nand on cubieboard.  
> Sample usage of nand-part: nand-part /dev/nand "linux 0"  
> Sample usage of nand-part2: nand-part2 /dev/nand 16 "boot 2048" "linux 0"  
> The difference of nand-part and nand-part2 is nand-part2 supports full repartition, nand-part will always keep the first partition untouched. nand-part2 is written by [patrickhwood](https://github.com/patrickhwood)

* **The swap partition is removed**  
  It's not neccssary as a buildin feature. If you really needs swap space, you can make it by youself using a program named `gparted`.

* **Kernel is recompiled with various features**  
