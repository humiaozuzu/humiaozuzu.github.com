---
title: OpenWrt 下让睡眠的 Mac 支持 iTunes 家庭共享功能
category: macOS
---

自己一直很喜欢用 iTunes 的家庭共享功能，可以在其他 iOS 设备中播放 Mac 中的音乐库。但是使用的过程中遇到了一个问题，当你的 Mac 进入睡眠状态时，家庭共享功能就失效了。查阅了 Apple 的官方帮助支持后，找到了解决方案，只需要简单 2 步设置。

1. 开启 Mac 上 iCloud 中的 Back to My Mac 功能
2. 在路由器中开启  NAT-PMP/UPnP 支持

第一步简单可以略去，第二部需要根据自己的路由器使用不通的策略，我自己使用的是刷了 openwrt 的路由，步骤如下：

首先安装 miniupnpd

``` bash
# opkg update
# opkg install miniupnpd
```

配置并开启 miniupnpd

``` bash
# uci set upnpd.config.enable_natpmp=1
# /etc/init.d/miniupnpd restart
```

检查一下是否开启成功，成功会有输出信息

``` bash
# logread | grep -i "\-pmp"
```

一切步骤 OK 后，就算你的 Mac 进入睡眠，在 iOS 客户端中也可以唤醒 Mac 继续享受 iTunes 家庭共享的音乐了 :)

## 参考资料

- [Universal Plug'n'Play and NAT-PMP on OpenWrt](http://wiki.openwrt.org/doc/howto/upnp)
- [OS X: Using and troubleshooting Back to My Mac with your iCloud account](http://support.apple.com/kb/HT4907)
- [About Wake on Demand and Bonjour Sleep Proxy](http://support.apple.com/kb/ht3774)
