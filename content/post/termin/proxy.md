---
title: 终端简易设置代理
description: 多平台终端设置代理。
date: 2023-10-11 00:00:00+0000
slug: httpproxy
categories:
    - Network Tools
tags:
    - proxy
weight: 1
---


### Linux

#### HTTP PROXY

```
export ALL_PROXY=http://127.0.0.1:1080
```

#### SOCKS5 PROXY

```
export ALL_PROXY=socks5://127.0.0.1:1080
```

#### 取消代理

```
unset http_proxy
unset https_proxy
```

### Windows

#### PowerShell

```
$env:ALL_PROXY="http://127.0.0.1:7890"
```

取消代理

```
$env:ALL_PROXY=""
```

#### CMD

```
set http_proxy=http://127.0.0.1:1080
set https_proxy=http://127.0.0.1:1080
```

取消代理

```
set http_proxy=
set https_proxy=
```

### 认证

适用于以上全部

`http://127.0.0.1:1080` 改为 ` http://user:pass@127.0.0.1:1080`

### 注意：部分软件是不走该Proxy，需要根据软件另行设置。