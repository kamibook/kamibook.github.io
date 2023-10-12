---
title: Golang跨平台编译
description: Linux上编译其它平台可执行文件。
date: 2023-10-12 00:00:00+0000
slug: golang
categories:
    - dev
tags:
    - golang
weight: 1

---


### Golang 跨平台编译

### 简介

Golang作为一个跨平台编程语言，提供了简易用的方式进行跨平台编译，以下将介绍如何在Linux系统上编译生成多个平台的可执行程序。

### 准备工作

操作环境

• Golang  
• Linux x86_64

### 设置环境变量

```
CGO_ENABLED=0  // 禁用CGO
GOOS=windows  // 目标平台是windows
GOARCH=amd64  // 目标处理器架构是amd64
```

### 编译

```
go build
```

### 其它平台

查询Golang支持的平台跟架构

```
go tool dist list
```

输出

```
aix/ppc64
android/386
android/amd64
android/arm
android/arm64
darwin/amd64
darwin/arm64
dragonfly/amd64
freebsd/386
freebsd/amd64
freebsd/arm
freebsd/arm64
illumos/amd64
ios/amd64
ios/arm64
js/wasm
linux/386
linux/amd64
linux/arm
linux/arm64
linux/loong64
linux/mips
linux/mips64
linux/mips64le
linux/mipsle
linux/ppc64
linux/ppc64le
linux/riscv64
linux/s390x
netbsd/386
netbsd/amd64
netbsd/arm
netbsd/arm64
openbsd/386
openbsd/amd64
openbsd/arm
openbsd/arm64
openbsd/mips64
plan9/386
plan9/amd64
plan9/arm
solaris/amd64
windows/386
windows/amd64
windows/arm
windows/arm64
```
