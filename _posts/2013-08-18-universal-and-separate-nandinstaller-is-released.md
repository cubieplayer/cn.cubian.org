---
layout: post
title: "Universal and separate nandinstaller is released"
categories: 
tags:
---
I created a separate package of **nandinstaller** which supports A10 and A20 regardless of the kernel version.
To install it, follow the [tutorial](http://cubian.org/2013/08/09/cubian-update-is-available/) adds the GPG key and configure the apt source properly.
> apt-get update && apt-get install cubian-nandinstall

The usage is pretty simple
> cubian-nandinstall

The nandinstaller is tested on several enviroments, but not covered all the releases.
Feel free to report bugs on github if you have any problems.
