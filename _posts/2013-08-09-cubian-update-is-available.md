---
layout: post
title: "Cubian update is available"
categories: 
tags:
---
cubian-update is tool to keep your kernel and modules updated.

Step 1. Add GPG key (root privilege is needed)
> wget -O - http://packages.cubian.org/cubian.gpg.key | apt-key add -

Step 2. Add apt source, add line to `/etc/apt/sources.list`
> deb http://packages.cubian.org/ wheezy main

Step 3. Install
> apt-get install cubian-update

Then execute `cubian-update` or `cubian-update -h` for more info.

# ScreenShot 
![cubian-update screenshot](http://cubieplayer.github.io/static_files/images/cubian-update.jpg)
