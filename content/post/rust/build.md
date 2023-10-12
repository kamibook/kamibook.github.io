---
title: RUST跨平台编译
description: Linux上编译其它平台可执行文件。
date: 2023-10-12 00:00:00+0000
slug: rust
categories:
    - dev
tags:
    - rust
weight: 1

---


### 简介

交叉编译就是在一个平台上可以编译生成另一个平台的可执行文件。主要介绍如何在Linux系统上编译生成多个系统的可执行文件。 

### 准备工作

操作环境

• Rust  
• Linux x86_64


### 添加Target

#### 首先查询支持的Target

已安装会在后面显示(installed)。

```
rustup target list
```

得出以下

```
aarch64-apple-darwin
aarch64-apple-ios
aarch64-apple-ios-sim
aarch64-linux-android
aarch64-pc-windows-msvc
aarch64-unknown-fuchsia
aarch64-unknown-linux-gnu
aarch64-unknown-linux-musl
aarch64-unknown-none
aarch64-unknown-none-softfloat
aarch64-unknown-uefi
arm-linux-androideabi
arm-unknown-linux-gnueabi
arm-unknown-linux-gnueabihf
arm-unknown-linux-musleabi
arm-unknown-linux-musleabihf
armebv7r-none-eabi
armebv7r-none-eabihf
armv5te-unknown-linux-gnueabi
armv5te-unknown-linux-musleabi
armv7-linux-androideabi
armv7-unknown-linux-gnueabi
armv7-unknown-linux-gnueabihf
armv7-unknown-linux-musleabi
armv7-unknown-linux-musleabihf
armv7a-none-eabi
armv7r-none-eabi
armv7r-none-eabihf
asmjs-unknown-emscripten
i586-pc-windows-msvc
i586-unknown-linux-gnu
i586-unknown-linux-musl
i686-linux-android
i686-pc-windows-gnu
i686-pc-windows-msvc
i686-unknown-freebsd
i686-unknown-linux-gnu
i686-unknown-linux-musl
i686-unknown-uefi
loongarch64-unknown-linux-gnu
mips-unknown-linux-musl
mips64-unknown-linux-muslabi64
mips64el-unknown-linux-muslabi64
mipsel-unknown-linux-musl
nvptx64-nvidia-cuda
powerpc-unknown-linux-gnu
powerpc64-unknown-linux-gnu
powerpc64le-unknown-linux-gnu
riscv32i-unknown-none-elf
riscv32imac-unknown-none-elf
riscv32imc-unknown-none-elf
riscv64gc-unknown-linux-gnu
riscv64gc-unknown-none-elf
riscv64imac-unknown-none-elf
s390x-unknown-linux-gnu
sparc64-unknown-linux-gnu
sparcv9-sun-solaris
thumbv6m-none-eabi
thumbv7em-none-eabi
thumbv7em-none-eabihf
thumbv7m-none-eabi
thumbv7neon-linux-androideabi
thumbv7neon-unknown-linux-gnueabihf
thumbv8m.base-none-eabi
thumbv8m.main-none-eabi
thumbv8m.main-none-eabihf
wasm32-unknown-emscripten
wasm32-unknown-unknown
wasm32-wasi
wasm32-wasi-preview1-threads
x86_64-apple-darwin
x86_64-apple-ios
x86_64-fortanix-unknown-sgx
x86_64-linux-android
x86_64-pc-solaris
x86_64-pc-windows-gnu
x86_64-pc-windows-msvc
x86_64-sun-solaris
x86_64-unknown-freebsd
x86_64-unknown-fuchsia
x86_64-unknown-illumos
x86_64-unknown-linux-gnu
x86_64-unknown-linux-gnux32
x86_64-unknown-linux-musl
x86_64-unknown-netbsd
x86_64-unknown-none
x86_64-unknown-redox
x86_64-unknown-uefi
```

#### 添加

```
rustup target add x86_64-unknown-linux-musl
```

### 编译

```
cargo build --release --target=x86_64-unknown-linux-musl
```
