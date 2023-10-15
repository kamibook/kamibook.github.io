---
title: Iptables：修改源IP
description: 修改源IP以利用多IP。
date: 2023-10-15 00:00:00+0000
slug: iptablessnat
categories:
    - Network Tools
tags:
    - Iptables
weight: 1
---

### 关闭原防火墙 

操作环境

• Almalinux9  

```
systemctl stop firewalld
systemctl disable firewalld
```

### 安装iptables-services

```
yum install iptables-services -y  #安装iptables
systemctl start iptables  #启动
systemctl enable iptables  #开机启动
```

### 开启端口（非必须）

```
iptables -I INPUT -m state --state NEW -m tcp -p tcp --dport 10000:50000 -j ACCEPT
iptables -I INPUT -m state --state NEW -m udp -p udp --dport 10000:50000 -j ACCEPT
```

### 创建用户

```
useradd -r a1
useradd -r a2
useradd -r a3
useradd -r a4
useradd -r a5
```

### 修改用户源IP

```
iptables -t nat -A POSTROUTING -m owner --uid-owner a1 -j SNAT --to-source 1.1.1.1
```

备注：以该用户启动的程序，TCP出网IP为设定的IP，一般情况不支持UDP。

### 保存规则

```
service iptables save
```
