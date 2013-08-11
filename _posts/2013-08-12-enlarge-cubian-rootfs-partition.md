---
layout: post
title: "Enlarge cubian rootfs partition"
categories: 
tags:
---
The rootfs partition on Cubian is 1GB. You may wants to enlarge the partition 
for more space. [Here](http://askubuntu.com/questions/24027/how-to-resize-a-ext4-root-partition-at-runtime) 
is a small tutorial.

For convenience, I have created a tool based on the tutorial named `cubian-resizefs`

# Installation

First, [Import GPG key and add apt source](http://cubian.org/2013/08/09/cubian-update-is-available)

Then,  
> apt-get update && apt-get install cubian-resizefs

# Usage

> cubian-resizefs END_SECTOR_POS

Replace **END_SECTOR_POS** to a number, if **END_SECTOR_POS** is not provided. 
It will occupy the whole SD-card.

# Notice

We modify the partition table using `fdisk` internally. It's always risky when you
do such things.So the old partition table is backuped. You can always restore the
partition table in case of any problem happens.

> dd if=PATH_TO_MBR_BAK of=/dev/MMC_DEVICE bs=1 count=64 skip=446 seek=446
