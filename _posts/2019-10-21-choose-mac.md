---
title: 苹果硬件选择指南 2019 版
category: macos
---

2019 年了，我手里最新的一台 MacBook 依然是 2015 年 mid 款，苹果多年持续的开倒车无数次阻止了我换机器的冲动。到今年，手里的这台 MacBook 终于出现了各种问题，电池膨胀、键盘使用太久部分按键不灵。好在，最后都自己折腾修好了（最麻烦的还是为了换新键盘自己买了 Topcase 手动更换）。

为什么不换硬件系统更好的 Windows 呢？这么多年 Windows 是一直在进步，但是用户付费习惯、开发者防破解需要的精力、开发者工具、付费软件生态，硬件易用性上依旧差距甚远。

既然非 macOS 不可，剩下的选择也就不多了。

### 1. 2016 年后的 MacBook Pro

新款 MacBook Pro 问题多到无法正常使用，直接放弃

- 转接口麻烦，type-c 并不好用
- WI-FI 故障多
- 散热差，本来旧版就差，新款为了做薄问题更加严重，降频后的性能惨不忍睹
- 风扇吵
- 蝶式键盘，我**所有**买新款 MacBook 的朋友键盘都出问题了
- 鸡肋的 Touch Bar，导致开发者无法正常使用键盘
- 没有了发光的 Logo，失去了灵魂

### 2. Mac mini and iMac (Pro)

Mac mini 体积小，散热不好。因为没有独显，唯一的扩展方法就是 eGPU 盒子，一个盒子花费要 2000 块，体积和 ITX 机箱一样大了。

iMac 一体化的更不考虑了。

### 3. MacBook Pro 2015

唯一一款正常的笔记本，性能到现在依然堪用，要求不高可以继续选择这款。途径是二手市场，价格 6-7K 左右可以收到在保或者状态比较新的。

### 4. 垃圾桶

通过收一台垃圾桶，自行升级硬件，具体请参考[「花了 10k 收获了一台 40k+ 的顶配垃圾桶」](https://mp.weixin.qq.com/s/zZ9cEVL4GTRzta-veYAz4Q)

## HackinTosh

**注意：使用黑苹果违反了EULA（Apple和你之间的约定），EULA 在各个国家都不尽相同，使用后果自负。**

2019 年 HackinTosh 已经到达了完美状态，因为 Lilu 系列的驱动在 2019 年已经完美，EFI 中加载好**通用**驱动，就可以安装启动了，不用关闭 SIP，不修改任何系统文件(Vanilla Install)；功能上一切和原生一样，包括 sidecar、蓝牙 WI-FI、Magic 系列硬件等。

### 一点疑问

Q: 黑苹果花时间吗，以及值得花时间吗？

A: 驱动已经已经不花时间了，关于值得不，白苹果你花时间也无法改变 ╮(╯▽╰)╭

Q: 现在有多稳定？

A: 稳定到可以在 Developer Beta 出来的第二天早上就跟着更新了（现在99%不会有问题，有也只是加个启动参数的事，insanelymac 论坛上都已贴好了）

Q: 为什么推特上那么多人说不稳定？

A: 硬件买错了，硬件不会装，看中文资料，路由器背锅！

Q: 听说苹果有个 T2 安全芯片？

A: iMac Pro 2019 没有 T2 芯片，够你安全用 10 年了。

### 缺点

- 如果买的硬件有一堆 RGB 灯，可能需要安装 Windows 才可以关闭

### 优点

- 用最简单的一体式水冷带 9700K 无压力，再无噪音和发热
- WI-FI 完美无故障
- 稳定性更好。你没有听错，因为一堆问题都是因为笔记本/Mac Mini 性能太差 ╮(╯▽╰)╭
- Catalina 已经原生支持了 RX 5700XT
- 再花 400 买一块 SSD，双系统工作娱乐两不误，Mac 下 Parallels Desktop 还可以使用这块盘上的 Windows 系统
- 成本只要 1/4 到 1/6 就可以组装一台 ITX 超小机箱的性能怪兽

### 此外的一些建议和注意点

- 选对硬件很重要（推荐选我下面提供的完美硬件）
- 亲力亲为可以学到很多硬件和系统层的知识，对未来诊断问题很有帮助
- 只看英文论坛

简单说一下流程

1. 先去 tonymacx86 的 [Buyer's Guide](https://www.tonymacx86.com/buyersguide/building-a-customac-hackintosh-the-ultimate-buyers-guide/) 挑合适的硬件
2. 去 tonymacx86/insanelymac 的经典 build 教程中找和自己主板一样的，学习安装的流程，蓝牙型号参考[这里](https://www.tonymacx86.com/threads/broadcom-wifi-bluetooth-guide.242423/)

### 我选择的完美硬件

怎样才能算完美呢？至少要 clover 配置文件几乎零修改。

- [ITX](https://pcpartpicker.com/list/xMkZf9) 因为网站未收录需要的网卡，需要额外购买一个 DW1560
- [mATX](https://pcpartpicker.com/list/Cggf9G) 记得选同型号的无 WI-FI 的主板，因为网站未收录无 WI-FI 的主板

硬件的建议

- 除了主板、WI-FI/蓝牙模块不变，其他的按自己需求换到兼容硬件就好
- 如果要换主板，不推荐选 ASRock 的
- 显卡推荐尽量用蓝宝石的
- 如果想要 Windows 装双系统用，推荐额外买一块 SATA3 860 EVO
- SSD 不要选 970 EVO Plus 和 三星 PM981
- 显示器请用 DP 接口

我参考的[教程](https://www.tonymacx86.com/threads/the-everything-works-asus-z390-i-gaming-i7-8700k-sapphire-rx580-pulse-build.272572/)（非常推荐看这篇，因为是 Vanilla Install 而且有很多额外的知识）

我组好的机器 CPU 跑分在[Geekbench Mac](https://browser.geekbench.com/mac-benchmarks) 里面排第一，成本只要 6K+。

### 外接键盘和触控板

我使用的是 Magic Trackpad 和 Magic keyboard 的新款，为了接近原生 MacBook 的体验，我把 trackpad 放到了键盘的下面，这样会带来误触的问题，解决方法也很简单，开启 BetterTouchTool 的 「Mirror complete Magic Trackpad orientation for "upside-down" usage.」

![Magic](/assets/images/magic-up-down.jpg)

### 多设备数据同步问题

目前只推荐 Dropbox 的 [Smart Sync](https://www.dropbox.com/smart-sync) 功能，一次性解决数据的备份和同步问题，丢掉所有的硬盘和 NAS，关闭 Time machine。
