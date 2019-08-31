---
title: "使用 iTunes 管理音乐"
category: macOS
---

获取音乐
------

我现在是从虾米下载，自己买了一年的会员，还有几千首歌曲的下载余额。虾米中没有的，从 Google 或者 VeryCD 中也可以找到盗版。

格式上我选择了 MP3，原因是我的耳朵听不出有啥区别，当然更重要的是 iTunes 不支持这些格式，全用 MP3 会少很多折腾。

音乐预处理
--------

预处理包括了格式转换个编码修正。

对于下载下来的部分无损格式，需要先转码；由于很多分享者的 Windows 系统默认用的 GBK 编码，所以音乐的 ID3 tag（里面存放了当前音乐的信息，比如作者，专辑名等）的也是一样的编码，苹果下的 iTunes 导入这些音乐后用 UTF-8 解码就出现了一堆乱码了。

这堆问题我都是用虚拟机开千千静听解决的，OS X 下已经折腾过，没有合适的工具了。

音乐管理
------

下面进入重点了，将前面处理好的 MP3 文件拖进 iTunes 就导入 iTunes 音乐库了。

### 编辑专辑信息

选中刚刚导入的音乐编辑他们的信息，一般来说我们只需要编辑专辑名，作者还有封面。（Tips:在 Google Images 里面搜索专辑名等信息就可以找到专辑封面了）

![iTunes Album Info](/assets/images/itunes-album-info.png)

### 专辑有多个艺术家

有的时候一个专辑可能有多个作者，此时 iTunes Library 中不会将这些歌曲显示为同一个专辑，我们需要在这些音乐的信息中勾选上「专辑的一部分」

![iTunes Album Part](/assets/images/itunes-album-part.png)

并填上「专辑艺术家」

![iTunes Album Part](/assets/images/itunes-album-artist.png)

### 专辑有多张CD

当一个专辑有多个CD的时候，我们只需要在最开始的情况中多添加CD信息就可以了，当然不同CD的部分需要分开编辑。

![iTunes Album CD](/assets/images/itunes-album-cd.png)

后记
----

iTunes是一个非常好的「音乐播放器/音乐管理」的软件，彻底解决了我以前用千千静听时专辑太多无法管理的问题，而且看着音乐都很「干净」是多么的赏心悦目。

![iTunes](/assets/images/itunes.jpg)

最近在用 Google Music 听音乐时，将 iTunes Library 中的音乐直接导入就可以播放了，专辑信息都完好无损，大赞！

![Google Music](/assets/images/google-music.png)

我喜欢苹果的产品以及哲学，慢慢的引导客户用正确的方法做一件事情，进而养成良好的习惯，高效的使用软件。

一味的迎合用户只能造成 IE 这样的悲剧，M$ 永远不知反省，只能在错误的道路上越走越远。
