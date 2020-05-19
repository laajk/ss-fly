一键脚本安装shadowsocks/shadowsocksR/V2Ray + 开启bbr
---

一键脚本搭建shadowsocks/shadowsocksR/V2Ray + 设置开启自启动 + 升级内核&开启bbr加速。

## 支持系统
CentOS 6+

Debian 7+

Ubuntu 12+

## 使用教程
下载一键搭建ss脚本文件
```BASH
sudo  git clone https://github.com/suniceman/ss-fly
```

安装
```BASH
ss-fly/ss-fly.sh -ssr
```
如果需要改密码或者改端口，只需要重新再执行一次搭建ss脚本代码就可以了，或者修改/etc/shadowsocks.json这个配置文件。

## 修改
```BASH
启动：/etc/init.d/ss-fly start
停止：/etc/init.d/ss-fly stop
重启：/etc/init.d/ss-fly restart
状态：/etc/init.d/ss-fly status
查看ss链接：ss-fly/ss-fly.sh -sslink
卸载 ss-fly/ss-fly.sh -uninstall
修改配置文件：vim /etc/shadowsocks.json
```

## 一键开启BBR加速
```BASH
ss-fly/ss-fly.sh -bbr
```

判断BBR加速有没有开启成功。输入以下命令：
```
sysctl net.ipv4.tcp_available_congestion_control
```
如果返回值为：
```
net.ipv4.tcp_available_congestion_control = bbr cubic reno
```
后面有bbr，则说明已经开启成功了。
