---
title: PING工具：RNP
description: RUST写的开源高性能L4网络PING工具，具有TCP及UDP PING。
date: 2023-10-11 00:00:00+0000
categories:
    - Network Tools
tags:
    - Ping
weight: 1
---

## 作者[GITHUB](https://github.com/r12f/rnp)

    
### 简单示例
```
PS D:\bin> ./rnp.exe 1.1.1.1:22
Rnp - r12f (r12f.com, github.com/r12f) - A simple layer 4 ping tool for cloud.

Start testing TCP 1.1.1.1:22:
Reaching TCP 1.1.1.1:22 from 192.168.31.86:18485 succeeded: RTT=23.80ms
Reaching TCP 1.1.1.1:22 from 192.168.31.86:18486 succeeded: RTT=23.83ms
Reaching TCP 1.1.1.1:22 from 192.168.31.86:18487 succeeded: RTT=20.84ms
Reaching TCP 1.1.1.1:22 from 192.168.31.86:18488 succeeded: RTT=24.95ms

=== Connect statistics for TCP 1.1.1.1:22 ===
- Connects: Sent = 4, Succeeded = 4, Failed = 0 (0.00%).
- Round trip time: Minimum = 20.84ms, Maximum = 24.95ms, Average = 23.35ms.
PS D:\bin>
```

### 多线程并发并省略输出
```
PS D:\bin> ./rnp.exe 1.1.1.1:22 -p 10 -n 100 -q
Rnp - r12f (r12f.com, github.com/r12f) - A simple layer 4 ping tool for cloud.

Start testing TCP 1.1.1.1:22:
100 pings finished.

=== Connect statistics for TCP 1.1.1.1:22 ===
- Connects: Sent = 100, Succeeded = 100, Failed = 0 (0.00%).
- Round trip time: Minimum = 17.49ms, Maximum = 28.72ms, Average = 23.27ms.
PS D:\bin>
```
参数
```
-p 10  #设置线程数，默认1
-n 100 # 设置PING数，默认4
-q #设置省略PING输出，默认全部输出
```
