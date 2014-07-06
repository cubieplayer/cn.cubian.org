---
layout: post
title: "解决Cubieboard2的稳定性问题"
categories: [news]
tags:
---
有一些在Cubieboard 2稳定性问题上的报告 [1](http://www.cubieforums.com/index.php/topic,952.msg13152.html#msg13152) [2](http://www.cubieforums.com/index.php/topic,2472.msg17784.html#msg17784) [3](http://www.cubieforums.com/index.php/topic,2696.msg17764.html#msg17764)，更多查看 [#319](https://github.com/cubieplayer/Cubian/issues/319)。引用 [Siarhei Siamashka](https://github.com/ssvb) 的解释如下:

<pre>
It has been confirmed that a substantial percentage of cubieboard2 and cubietruck users are having stability issues. These issues are caused by having various voltages optimistically configured way too low. Because each unit has its own tolerances, not everyone can easily reproduce these problems.
</pre>

[这里](https://groups.google.com/forum/#!searchin/linux-sunxi/dcdc3/linux-sunxi/1Orj-ukBb6s/qjfAh_NrL3YJ) 有一个关于此问题详尽的讨论。

#解决此问题的方法
1. 方案 A  
手工为script.bin打 [这个补丁](http://cubieplayer.github.io/static_files/temp/script.patch)。
2. 方案 B  
从[这里](https://github.com/mmplayer/cubian-updates/blob/a20-3.4.79_2/boot/script.bin?raw=true)下载并覆盖已经修正过的script.bin。
3. 方案 C  
运行 <code>cubian-update --update-board-cfg</code>

#验证问题是否解决
1. 第一步，安装最新的内核  
<code>apt-get update && apt-get install linux-image</code>
2. 第二步，安装硬件测试软件 
<code>apt-get install cpuburn-sunxi lima-memtester</code>
3. 第三部，执行测试  
<code>cpuburn-sunxi</code> 测试在CPU负担比较重的情况下是否会过热死机。  
<code>cpufreq-stress-test-sunxi</code> 测试CPU在各个频率下是否稳定运行。   
<code>lima-memtester</code> 测试内存是否正常。

#屏幕截图
![cpuburn-sunxi 运行截图](http://cubieplayer.github.io/static_files/images/cpuburn-sunxi.png)
![cpu-freq-stress-test 运行截图](http://cubieplayer.github.io/static_files/images/cpu_freq_stress_test.png)
![lima-memtester 运行截图](http://cubieplayer.github.io/static_files/images/lima-memtester.png)
