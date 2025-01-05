---
title: "给 Golang 开发者的 Rust 私房菜 02 变量与可变性"
categories: [ "Rust" ]
tags: [ "rust" ]
draft: false
slug: "rust-tutorial-02"
date: "2024-12-30T16:34:00+0800"
---

## Bilibili

{{< bilibili BV1ZX63YqEFa >}}

建议前往 B 站观看哦！

---

## 使用 RustRover

RustRover 是 JetBrains 专为 Rust 语言开发的独立 IDE，致力于提供专业的 Rust 开发环境。RustRover 源自多年来在 JetBrains IDE 中的 Rust 插件支持经验，具备完整的 Rust 功能支持，包括深度学习驱动的全行代码补全、改进的 Cargo 管理、强大的调试工具和数据库支持等功能，旨在优化开发者的 Rust 工作流。

RustRover 引入了灵活的许可模式：个人非商业用途可以免费使用，而商业用途则需购买付费许可。这种模式允许独立开发者免费使用专业级的 Rust 开发环境。此外，RustRover 还能与 JetBrains 的其他工具无缝集成，便于协作和版本控制，是适合团队和个人项目的理想选择。

## 变量声明与可变性

### 变量声明的差异

在 Go 中，我们使用 `var` 关键字或 `:=` 简写来声明变量：

```go
var name string = "Go"
age := 42
```

最大的区别在于：

1. Rust 默认所有变量都是不可变的（immutable）
2. 需要显式使用 `mut`关键字来声明可变变量
3. Rust 具有强大的类型推导能力，通常不需要显式声明类型

而在 Rust 中，我们使用 let 关键字：

```rust
let name = "Rust";
let mut age = 42;
```

### 变量重影（Shadowing）

Rust 独特的特性之一是允许变量重影：

```rust
let x = 5;

let x = x + 1;

{
  let x = x * 2;
  println!("x 在当前作用域的值是: {x}");
}

println!("x 的值是: {x}");
```

这与 Go 中的变量重声明是不同的概念，Rust 的重影允许我们复用变量名但可以改变类型：

```rust
let text = "hello";
let text = text.len(); // 从字符串变为数字
```

## 实践建议

作为 Go 开发者，需要特别注意：

- 优先使用不可变变量，这是 Rust 的最佳实践
- 当确实需要修改变量值时，再使用 `mut` 关键字
- 合理利用变量重影特性可以让代码更清晰
