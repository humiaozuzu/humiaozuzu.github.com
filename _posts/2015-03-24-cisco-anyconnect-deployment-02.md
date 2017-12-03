---
title: Cisco AnyConnect 部署完全教程（2）：iPhone Configuration Utility 部署配置文件
category: GFW
---

先将你第一步中生成的用户证书从服务器下载到本地

``` bash
scp 8.8.8.8:/opt/ocserv/ca/user.p12 .
```

### 添加新的配置文件

![icu](/assets/images/icu01.jpg)

新添加配置文件，填好名字和标识符

![icu](/assets/images/icu02.jpg)

将刚刚从服务器上 copy 下来的证书导入，并输入证书密码

![icu](/assets/images/icu03.jpg)


配置 Cisco AnyConnect，选对vpn类型，填写服务器地址，认证方式为证书，证书文件选中刚刚导入的。

将导出的配置文件放到服务器上面，iPhone 上用 Safari 浏览器（Chrome 不可以）访问服务器地址，就可以成功安装配置文件了。
