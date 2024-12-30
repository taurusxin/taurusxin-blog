---
title: "给 Golang 开发者的 Rust 私房菜 01 千里之行，始于足下"
categories: [ "Rust" ]
tags: [ "rust" ]
draft: false
slug: "rust-tutorial-01"
date: "2024-12-30T01:20:00+0800"
---

## 视频

{{< bilibili BV1BG6eYPE7L >}}

建议前往 B 站观看哦！

## 课程笔记

### Rust 简介

**Rust** 是一门注重 **内存安全** 和 **高性能** 的系统编程语言，通过所有权机制避免常见的内存错误。自 **2021 年 Linux 内核 5.13 版本**起，Rust 被正式引入，用于提高内核模块（如驱动程序）的安全性，减少内存管理漏洞。目前，Rust 在内核中的应用仍处于初期阶段，未来可能会逐步扩大。

### 安装

- 官方网站：<https://www.rust-lang.org/>

- Homebrew

```shell
brew install rust
```

### HelloWorld

```rust
fn main() {
  println!("Hello, World!");
}
```

### Hello Cargo

建立 cargo 项目

```shell
cargo new hello_cargo
```

源代码

```rust
fn main() {
  println!("Hello, cargo!");
}
```

构建项目

```shell
cargo build
```

运行项目

```shell
cargo run
```

检查项目

```shell
cargo check
```
