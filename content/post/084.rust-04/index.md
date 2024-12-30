---
title: "给 Golang 开发者的 Rust 私房菜 03 数据类型"
categories: [ "Rust" ]
tags: [ "rust" ]
draft: false
slug: "rust-tutorial-03"
date: "2024-12-30T16:36:00+0800"
---

## 视频

{{< bilibili BV1ZX63YqEMw >}}

建议前往 B 站观看哦！

## 课程笔记

### Rust 的数据类型概述

Rust 是一门静态类型语言，在编译时就会进行严格的类型检查。

Rust 的数据类型可以分为两大类：

1. **标量类型（Scalar Types）**：
   - 单个值，如整数、浮点数、布尔值、字符。
2. **复合类型（Compound Types）**：
   - 包含多个值的类型，如元组和数组。

与 Golang 对比：

- Rust 的类型定义更加严格，默认不会隐式类型转换。
- 更注重内存安全和性能优化。

### 标量类型

#### 整数类型

- **有符号整数（Signed）：** `i8`, `i16`, `i32`, `i64`, `i128`, `isize`
- **无符号整数（Unsigned）：** `u8`, `u16`, `u32`, `u64`, `u128`, `usize`

`isize`和`usize`类型取决于运行程序的计算机的体系结构：如果使用 64 位体系结构，则为 64 位；如果使用 32 位体系结构，则为 32 位。

> 默认类型是 `i32`，因为它的性能较好。

##### 示例

```rust
fn main() {
  let x: i32 = 10;
  let y: u8 = 255;
  println!("x: {}, y: {}", x, y);
}
```

溢出行为：

- 调试模式：触发 panic。
- 发布模式：会循环取值。

#### 浮点类型

- `f32`: 32 位浮点数
- `f64`: 64 位浮点数（默认）

##### 示例

```rust
fn main() {
  let pi: f64 = 3.14159;
  println!("Pi: {}", pi);
}
```

#### 布尔类型

- 类型为 `bool`。
- 值为 `true` 或 `false`。

##### 示例

```rust
fn main() {
  let is_rust_fun = true;
  println!("Rust is fun: {}", is_rust_fun);
}
```

#### 字符类型

- 使用单引号定义。
- 支持 Unicode，长度为 4 字节。

##### 示例

```rust
fn main() {
    let emoji = '😊';
    println!("Emoji: {}", emoji);
}
```

### 复合类型

#### 元组（Tuple）

- 可包含**多种不同类型**的值。
- 元组的长度是**固定**的。

##### 示例

```rust
fn main() {
  let tup: (i32, f64, u8) = (500, 6.4, 1);
  let (x, y, z) = tup; // 解构元组
  println!("The value of y is: {}", y);
}
```

#### 数组（Array）

- 固定长度，元素类型**必须相同**。
- 与 Golang 的切片不同，Rust 的数组大小在编译期就确定。

##### 示例

```rust
fn main() {
  // 类型推导
  let arr = [1, 2, 3];
  // 指定类型
  let arr: [i32; 3] = [1, 2, 3];

  println!("Array: {:?}", arr);
}
```

### 类型转换

Rust 不支持隐式类型转换，必须显式转换。

- 使用 `as` 关键字进行类型转换。

##### 示例

```rust
fn main() {
  let x = 10;
  let y = x as f64 / 3.0;
  println!("y: {}", y);
}
```

---

### 实践建议

- **优先使用类型推导**：Rust 的类型推导可以减少代码冗余。
- **注意整数溢出**：调试模式下会 panic，发布模式下会循环取值。
