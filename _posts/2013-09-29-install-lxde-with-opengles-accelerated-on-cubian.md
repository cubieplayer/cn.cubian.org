---
layout: post
title: "在Cubian上安装显卡加速的LXDE桌面环境"
categories: [news]
tags: 教程
---
Cubian 默认没有安装桌面，但是现在你可以轻松的安装它。

# 首先
确保你的根文件系统有大于1GB的空间，可以使用[cubian-resizefs](http://cn.cubian.org/2013/08/12/enlarge-cubian-rootfs-partition/)这个工具扩大根文件系统分区。

# 简单来说
依次执行
> apt-get update
> cubian-update  
> apt-get install xserver-xorg-core xinit xserver-xorg-video-sunximali sunxi-disp-test lxde-core 
> usermod -a -G video cubie

如果一切正常，你就会得到一个经显卡加速的LXDE桌面。

# 效果截图
![cubian 安装了LXDE后的效果图](http://cubieplayer.github.io/static_files/images/cubian-lxde-gles.png)

# 详细安装步骤
1.	Cubian update  
	这保证了你的Cubian能够获得最新的硬件支持。
1.	安装 **xserver-xorg-core** 和 **xinit**  
	我们只需要核心包，不要安装 **xserver-xorg** 这个包，它很大，而且包含了许多我们不需要的文件。
1.	安装 **xserver-xorg-video-sunximali** 和 **sunxi-disp-test**  
	这是显卡驱动和驱动测试程序（ [ssvb](https://github.com/ssvb/)） 致谢。
	现在X窗口系统应该就可以正常工作了，你可以进行如下测试 
	
	> xinit /usr/bin/sunxi_disp_test -- :0
	
	如果你看到了一个灰色背景上的480*480像素的彩色三角形，那么代表一切正常。你可以安全的进行下一步。
1.	安装 lxde
1.	把用户 cubie 添加到 **video** 组, 这样他才可以正常访问显卡设备。
1.	再次执行测试程序，看看是否正常。从开始菜单打开 lxtermial 执行

	> xinit /usr/bin/sunxi_disp_test
