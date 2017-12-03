---
title: Cisco AnyConnect 部署完全教程（3）：iPhone 上使用 Launcher 一键连接
category: GFW
---

Launcher [下载地址](https://itunes.apple.com/us/app/launcher-notification-center/id905099592?mt=8)

![Launcher](/assets/images/launcher01.jpg)
添加入口

开启和关闭的 url scheme 分别是 `anyconnect://connect?name=Cisco&onsuccess=anyconnect:close` 和 `anyconnect://disconnect/?onsuccess=anyconnect:close`，注意参数里面的name需要和你起的名字完全对应。

关于 Cisco AnyConnect 更详细的文档可以看[这里](http://www.cisco.com/c/en/us/td/docs/security/vpn_client/anyconnect/anyconnect30/administration/guide/anyconnectadmin30/acmobiledevices.html)


![Launcher](/assets/images/launcher02.jpg)
最后效果
