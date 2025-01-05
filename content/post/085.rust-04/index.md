---
title: "给 Golang 开发者的 Rust 私房菜 04 函数、表达式和语句"
categories: [ "Rust" ]
tags: [ "rust" ]
draft: false
slug: "rust-tutorial-04"
date: "2025-01-05T22:45:00+0800"
---

## Bilibili

{{< bilibili BV1TVrTYCESM >}}

建议前往 B 站观看哦！

---

## 函数

### 定义与调用

- 使用 `fn` 关键字定义函数。

- 参数需要显式声明类型。

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b
}

fn main() {
    let result = add(2, 3);
    println!("Result: {}", result);
}
```

### 返回值

函数的返回值是最后一个表达式的值，无需显式 `return`。

```rust
// 使用 return
fn square(x: i32) -> i32 {
    return x * x;
}

// 无需显式 return
fn square(x: i32) -> i32 {
    x * x       // 结尾没有分号
}
```

使用空元组 `()` 表示函数无返回值。

```rust
fn greet() {
    println!("Hello, Rust!");
}

fn greet() {
    println!("Hello, Rust!")    // 无分号，返回值是 `()`
}
```

### 表达式和语句

- **表达式**会返回一个值，例如 `a + b` 或数字 `42`。
- **语句**不返回值，例如变量声明 `let x = 5;`。
- 函数中的最后一行是表达式，因此不需要 `return`。

```rust
fn calculate(x: i32) -> i32 {
    let doubled = x * 2;    // 语句，定义变量
    doubled + 1             // 表达式，最终返回值是 (x * 2) + 1
}
```

- Rust 中的代码块 `{}` 是一个表达式，其返回值为块中最后一个表达式的值。

```rust
fn main() {
    let result = {
        let a = 10;
        let b = 20;
        a + b      // 块的返回值
    };
    println!("Result: {}", result);    // 输出 30
}
```

## 实践建议

- 尽量利用表达式简化函数逻辑，减少显式 `return`。
- 使用代码块返回值时，保持代码可读性，避免嵌套过深。
