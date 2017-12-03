---
title: Cisco AnyConnect 部署完全教程（1）：服务器部署
category: GFW
---

基本的步骤都通过 shell 脚本完成，程序仅仅在 Ubuntu Server 12.04/14.04 下简单测试过，[Github 地址](https://github.com/humiaozuzu/ocserv-build)。不放心的朋友们可以自己一步步执行脚本里面的代码。所有程序都需要在 Root 用户下执行。

## 编译安装 OCServ

``` bash
bash build-src.sh
```

安装路径在 `/opt/ocserv` 下，安装成功后，测试一下

``` bash
cd /opt/ocserv
LD_LIBRARY_PATH=/opt/local/lib ./sbin/ocserv -h
```

如果可以正常打印帮助信息就说明安装成功了。

## 配置证书

``` bash
bash build-ca.sh
```

执行脚本之前，需要配置的地方：

1. AUTHOR 填维护者或者公司的名字
2. VPN 填你给这个vpn的取名
3. DOMAIN 服务器的域名，如果没域名用 ip

最终证书都生成在 `/opt/ocserv/ca` 目录下，其中用户证书会要求你输入密码，记得一定要输入，并记住。

## 配置 iptable/添加 upstart 脚本

### iptable 转发

先开启转发：

``` bash
iptables -t nat -A POSTROUTING -s 10.0.1.0/24 -o eth0 -j MASQUERADE
```

如果是 openvz 的主机：

``` bash
iptables -t nat -A POSTROUTING -s 10.0.1.0/24 -o venet0 -j MASQUERADE
```

然后在 `/etc/sysctl.conf` 中添加 `net.ipv4.ip_forward=1`，并运行下面的脚本使之生效：

``` bash
sysctl -p
```

### iptable 持久化

``` bash
iptables-save > /etc/iptables.rules
cat << EOF > /etc/network/if-pre-up.d/iptablesload
#!/bin/sh
iptables-restore < /etc/iptables.rules
exit 0
EOF
chmod +x /etc/network/if-pre-up.d/iptablesload
```

### 添加 upstart 脚本

``` bash
mv config/ocserv.conf /etc/init/
```

## 测试运行

添加 ocserv 配置文件 + 测试连接

``` bash
mv config/config /opt/ocserv/etc/
LD_LIBRARY_PATH=/opt/local/lib ./sbin/ocserv -c etc/config -f -d 1
```

如果连接成功了，那么就开启服务

``` bash
service ocserv start
```
