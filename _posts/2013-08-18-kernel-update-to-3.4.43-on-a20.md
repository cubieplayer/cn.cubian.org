---
layout: post
title: "Kernel update to 3.4.43 on A20"
categories: 
tags:
---
Cubian for cubieboard2(A20) has update kernel from 3.3.0 to 3.4.43.
The good news is **gpio_sunxi** and **mali** drivers is working on cubieboard2 now.
To autoload these modules,uncomment the associate line in **/etc/modules**.
Aslo, the Ralink wireless driver is compiled but not tested, the driver name is `rt5370sta`.

You need to update your [cubian-update](http://cubian.org/2013/08/09/cubian-update-is-available/) to latest version(1.0-3). To update, run
> apt-get update && apt-get install cubian-update

To update the kernel, simply run
> cubian-update

If you have problems, please enable verbose mode to get more details
> cubian-update -v

To downgrade the kernel after updated, run
> cubian-update --revert-firmware

If you are using the new kernel, The nandinstaller won't work due to the nand driver changes.
Please use the new [universal nandinstaller](http://cubian.org/2013/08/18/universal-and-separate-nandinstaller-is-released) instead.

Enjoy the new kernel, Feel free to report on github if you have any problems.
