---
title: 苹果硬件选择指南 2020 版
category: macos
---

2020 年，我手里最新的一台 MacBook 依然是 2015 年 mid 款，苹果多年持续的开倒车无数次阻止了我换机器的冲动。到 2019 年，手里的这台 MacBook 终于出现了各种问题，电池膨胀、键盘使用太久部分按键不灵。好在，最后都自己折腾修好了（最麻烦的还是为了换新键盘自己买了 Topcase 手动更换）。

为什么不换硬件系统更好的 Windows 呢？这么多年 Windows 是一直在进步，但是用户付费习惯、开发者防破解需要的精力、开发者工具、付费软件生态，硬件易用性上依旧差距甚远。

既然非 macOS 不可，剩下的选择也就不多了。

### 1. 16 寸 MacBook Pro

作为 2015 MacBook Pro 的升级版，问题更多
- T2 引起的系统不稳定问题
- Thunderbolt 3 的各种问题（充电插错边 CPU 占满，显示器不兼容 CPU 占满等等）
- 外接显示器会引起风扇狂转的问题
- 散热差、风扇吵、鸡肋 Touch Bar、无发光 Logo 的老问题依旧存在

### 2. 2016 年后的 15 寸 MacBook Pro

新款 MacBook Pro 问题多到无法正常使用，直接放弃

- 转接口麻烦，Thunderbolt3 并不好用
- WI-FI 故障多
- 蝶式键盘，我**所有**买新款 MacBook 的朋友键盘都出问题了
- 散热差，本来旧版就差，新款为了做薄问题更加严重，降频后的性能惨不忍睹
- 风扇吵
- 鸡肋的 Touch Bar，导致开发者无法正常使用键盘
- 没有了发光的 Logo，失去了灵魂

### 3. Mac mini and iMac (Pro)

Mac mini 体积小，散热不好。因为没有独显，唯一的扩展方法就是 eGPU 盒子，一个盒子花费要 2000 起，体积还和 ITX 机箱一样大。

iMac 一体化的更不考虑了。

### 4. MacBook Pro 2015

唯一一款正常的笔记本，性能到现在依然堪用，要求不高可以继续选择这款。途径是二手市场，价格 6K 左右可以收到在保或者状态比较新的。

### 5. 垃圾桶

通过收一台垃圾桶，自行升级硬件，具体请参考[「花了 10k 收获了一台 40k+ 的顶配垃圾桶」](https://mp.weixin.qq.com/s/zZ9cEVL4GTRzta-veYAz4Q)

## HackinTosh

**注意：使用黑苹果违反了EULA（Apple和你之间的约定），EULA 在各个国家都不尽相同，使用后果自负。**

2019 年后 HackinTosh 已经到达了完美状态，因为 Lilu 系列的驱动在 2019 年已经完美，EFI 中加载好**通用**驱动，就可以安装启动了，不用关闭 SIP，不修改任何系统文件(Vanilla Install)；功能上一切和原生一样，包括 sidecar、蓝牙 WI-FI。

### 一点疑问

Q: 黑苹果花时间吗，以及值得花时间吗？

A: 驱动已经已经不花时间了。需要花时间的部分是，了解基础的 PC 的硬件知识（因为对于大部分苹果用户来说，问题都来自于不了解硬件）。关于值得不，白苹果你花时间也无法改变 ╮(╯▽╰)╭

Q: 现在有多稳定？

A: 稳定到可以在 Developer Beta 出来的第二天早上就跟着更新了（现在99%不会有问题，有也只是加个启动参数的事，insanelymac 论坛上都已贴好了）。但是如果你用的 OpenCore，不推荐升级 Developer Beta 版。

Q: 为什么 Twitter 上那么多人说不稳定？

A: 2019 年是分水岭，说不稳定的是这之前折腾的。

Q: 我应该等苹果的 ARM 机器吗？

A: 不用，原因如下。
- 很多人把本次迁移和当当年从 PPC 换到 Intel 做类比，但是实际上 2 件事是完全相反的。PPC 到 Intel 用户获得很多便利，如 Windows、x86 生态的基础库、更好的性能、虚拟化等。现在开倒车全部丢掉，自己 Laptop 那点用户量也想全部丢完？
- 这篇 [Linus Torvalds on Why ARM Won't Win the Server Space](https://www.realworldtech.com/forum/?threadid=183440&curpostid=183486) 里面提到的理由，对于 Apple 这次迁移理由也同样适用。
- 苹果这些年的硬件改革全部失败：
    - 3D Touch 砍了
    - FaceID 用户受难中（开始觉得不错的人在疫情期间的体验如何）
    - 蝶式键盘砍了
    - 改方向键砍了
    - Touch Bar 用户受难中
    - T2 用户受难中
    - ThunderBolt 3 用户受难中
    - 由此可见，硬件部门的人看起来不怎么靠谱。
- 就算苹果一不小心成功了，在本次发布会上也说到了会继续发布 Intel 10 代 CPU 的产品，以及 Mac Pro 专业用户也不会换 ARM，未来再用个 10 年肯定没问题。

### HackinTosh 缺点

- 需要你学习硬件的知识

### HackinTosh 优点

- 稳定性更好。你没有听错，因为一堆问题都是笔记本性能太差、垃圾的 T2 芯片和 Type-C 接口引起
- 用最简单的一体式水冷带 9700K 无压力，再无噪音和发热
- WI-FI 完美无故障
- UEFI BIOS 中超频/睿频配置随意切换
- Catalina 原生支持了 RX 5700XT
- Catalina 原生支持了 Intel 10 代 CPU
- 再花 400 买一块 SSD 装 Windows，双系统工作娱乐两不误，Mac 下 Parallels Desktop 还可以使用这块盘上的 Windows 系统
- 成本只要 1/5 就可以组装一台超小机箱的性能怪兽

### 此外的一些建议和注意点

- 选对硬件很重要（推荐选我下面提供的完美硬件）
- 亲力亲为可以学到很多硬件和系统层的知识，对未来诊断问题很有帮助
- 只看英文论坛

### 简单说一下流程

1. 去 tonymacx86/insanelymac 的经典 build 教程中找自己想要的主板
2. 对着教程购买主板，其他的按自己的需求调整就行调高或者调低 CPU/GPU/SSD 的配置，机箱水冷这些按喜好来。

### 硬件的建议

- 除了主板、WI-FI/蓝牙模块不变，其他的按自己需求换到兼容硬件就好
- 主板推荐 Asus/Gigabyte/MSI，不推荐 ASRock 的
- 显卡推荐尽量用蓝宝石的
- 如果想要 Windows 装双系统用，推荐额外买一块 860 EVO的 Sata 盘
- SSD 不要选 970 EVO Plus 和 三星 PM981
- 显示器请用 DP 接口
- mATX 硬件的价格会比 ITX 便宜不少，如果不追求特别小的机箱，mATX 可以省不少钱。

### 我推荐的硬件列表

#### 9 代 Intel CPU

- [i7-9700K+ITX](https://pcpartpicker.com/list/xMkZf9) 因为网站未收录需要的网卡，需要额外购买一个 DW1560
- [i7-9700K+mATX](https://pcpartpicker.com/list/Cggf9G) 记得选同型号的无 WI-FI 的主板，因为网站未收录无 WI-FI 的主板
- 以上两款硬件对应的[教程](https://www.tonymacx86.com/threads/the-everything-works-asus-z390-i-gaming-i7-8700k-sapphire-rx580-pulse-build.272572/)

#### 10 代 Intel CPU

- [i5-10500+mATX](https://pasotan.com/s/J2nneY) 必须使用 OpenCore，且需要 10.15.5 版本
- 以上硬件对应的[教程](https://www.tonymacx86.com/threads/micro-atx-build-msi-mag-b460m-mortar-i5-10500-rx470-open-core-catalina-10-15-5.299709/)

#### 推荐的通用教程

即使你用了前面文章里面的配置，也非常推荐下面的教程，因为是 Vanilla Install 而且有很多额外的知识

- [Clover Vanilla Install](https://hackintosh.gitbook.io/-r-hackintosh-vanilla-desktop-guide/) Clover 通用配置教程
- [OpenCore Desktop Guide](https://dortania.github.io/OpenCore-Desktop-Guide/) OpenCore 通用配置教程


### 外接键盘和触控板

我使用的是 Magic Trackpad 和 Magic keyboard 的新款，为了接近原生 MacBook 的体验，我把 trackpad 放到了键盘的下面，这样会带来误触的问题，解决方法也很简单，开启 BetterTouchTool 的 「Mirror complete Magic Trackpad orientation for "upside-down" usage.」

![Magic](/assets/images/magic-up-down.jpg)

### 多设备数据同步问题

目前只推荐 Dropbox 的 [Smart Sync](https://www.dropbox.com/smart-sync) 功能，一次性解决数据的备份和同步问题，丢掉所有的硬盘和 NAS，关闭 Time machine。
