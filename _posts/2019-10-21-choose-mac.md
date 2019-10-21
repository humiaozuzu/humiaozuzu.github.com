---
title: 苹果硬件选择指南 2019 版
category: macos
---

2019 年了，我手里最新的一台 MacBook 依然是 2015 年 mid 款，苹果多年持续的开倒车无数次阻止了我换机器的冲动。到今年，手里的这台 MacBook 终于出现了各种问题，电池膨胀、键盘使用太久部分按键不灵。好在，最后都自己折腾修好了（最麻烦的还是为了换新键盘自己买了 Topcase 手动更换）。

为什么不换硬件系统更好的 Windows 呢？这么多年 Windows 是一直在进步，但是用户付费习惯、开发者防破解需要的精力、开发者工具、付费软件生态，硬件易用性上依旧差距甚远。

既然非 macOS 不可，剩下的选择也就不多了。

### 1. 2016 年后的 MacBook

新款 MacBook 问题多到无法正常使用，直接放弃

- 转接口麻烦，type-c 并不好用
- 散热差，本来旧版就差，新款为了做薄问题更加严重，降频后的性能惨不忍睹
- 风扇吵
- 蝶式键盘，我**所有**买新款 MacBook 的朋友键盘都出问题了
- 鸡肋的 Touch Bar，导致开发者无法正常使用键盘
- 没有了发光的 Logo，失去了灵魂

### 2. Mac mini and iMac

Mac mini 体积小，散热不好。因为没有独显，唯一的扩展方法就是 egpu 盒子，一个盒子花费要 2000 块，体积还不小。

iMac 一体化的更不考虑了。


### 3. MacBook 2015

唯一一款正常的笔记本，性能到现在依然堪用，要求不高可以继续选择这款。途径是二手市场，价格 6-7K 左右可以收到在保或者状态比较新的。

### 4. 垃圾桶

通过收一台垃圾桶，自行升级硬件，具体请参考[「花了 10k 收获了一台 40k+ 的顶配垃圾桶」](https://mp.weixin.qq.com/s/zZ9cEVL4GTRzta-veYAz4Q)

## HackinTosh

**注意：使用黑苹果违反了EULA（Apple和你之间的约定），EULA 在各个国家都不尽相同，使用后果自负。**

2019 年 HackinTosh 已经到达了完美状态

- 成本只要 4/1 到 6/1 就可以组装一台性能怪兽
- 自己组装一体式水冷带9700K无压力，再无噪音
- 稳定性更好。你没有听错，因为一堆问题都是因为笔记本性能太差 ╮(╯▽╰)╭
- 因为 Lilu 生态的驱动已经完美，EFI 中加载好**通用**驱动，已经可以无侵入系统文件启动(Vanilla Install)
- 可以在 Developer Beta 出来的第二天早上就跟着更新了（现在非常稳定大概率不会有问题，有也只会是小问题，国外论坛上都已贴好了解决方法）

此外的一些建议和注意点

- 选对硬件很重要
- 亲力亲为可以学到很多硬件和系统层的知识，对未来诊断问题很有帮助
- 只看英文论坛

简单说一下流程

1. 先去 tonymacx86 的 [Buyer's Guide](https://www.tonymacx86.com/buyersguide/building-a-customac-hackintosh-the-ultimate-buyers-guide/) 挑合适的硬件
2. 去 tonymacx86/insanelymac 的经典 build 教程中找和自己主板一样的，学习安装的流程，蓝牙型号参考[这里](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/)

推荐下我选的[硬件(mini-ITX机箱)](https://pcpartpicker.com/list/fnM9Wb)以及我参考的[教程](https://www.tonymacx86.com/threads/the-everything-works-asus-z390-i-gaming-i7-8700k-sapphire-rx580-pulse-build.272572/)（非常推荐看这篇，因为里面有很多额外的知识）

组好的机器 CPU 跑分在[Geekbench Mac](https://browser.geekbench.com/mac-benchmarks) 里面排第一，成本只要 6K+。

### 外接键盘和触控板

我使用的是 Magic Trackpad 和 Macgic keyboard 的新款，为了接近原生 MacBook 的体验，我把 trackpad 放到了键盘的下面，这样会带来误触的问题，解决方法也很简单，开启 BetterTouchTool 的 「Mirror complete Magic Trackpad orientation for "upside-down" usage.」

![Magic](/assets/images/magic-up-down.jpg)

### 多设备数据同步问题

目前只推荐 Dropbox 的 [Smart Sync](https://www.dropbox.com/smart-sync) 功能，一次性解决数据的备份和同步问题，丢掉所有的备份硬盘，关闭了 Time machine。
