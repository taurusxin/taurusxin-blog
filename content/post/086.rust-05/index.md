---
title: "给 Golang 开发者的 Rust 私房菜 05 流程控制"
categories: [ "Rust" ]
tags: [ "rust" ]
draft: false
slug: "rust-tutorial-05"
date: "2025-01-05T22:57:00+0800"
---

## Bilibili

{{< bilibili BV1TVrTYkETR >}}

---

## 条件分支

- 使用 `if` 和 `else` 实现条件判断
- 使用 `else if` 实现多重条件判断

```rust
fn main() {
    // 单个条件
    let number = 10;

    if number > 5 {
        println!("Number is greater than 5");
    } else {
        println!("Number is less than or equal to 5");
    }
    
    // 多个条件
    let favorite_fruit = "apple";

    if favorite_fruit == "apple" {
        println!("I like apples.");
    } else if favorite_fruit == "banana" {
        println!("I like bananas.");
    } else {
        println!("I like other fruits.");
    }
}
```

在 `let` 中使用 `if`

```rust
fn main() {
    let number = 6;
    let result = if number % 2 == 0 { "even" } else { "odd" };
    println!("Number is {}", result);
}
```

需要注意的是，`if`表达式的值取决于执行哪个代码块。这意味着 `if` 的每个分支可能产生的值必须是相同的类型，如果类型不匹配，如下例所示，我们将收到错误

```rust
fn main() {
    let number = 10;
    let result = if number % 2 == 0 { "even" } else { 5 };
    println!("Result is {}", result);
}
```

## 循环重复

Rust 具有三种循环： `loop` 、`while` 和 `for`

### loop 无限循环

使用 `loop` 关键字创建无限循环，它告诉 Rust 永远一遍又一遍地执行代码块，或者直到你明确告诉它停止为止

```rust
fn main() {
    let mut count = 0;
    loop {
        count += 1;
        if count > 5 {
            break;
        }
        println!("Count: {}", count);
    }
}
```

`break` 允许从循环结果中返回值，传递到代码的其余部分

```rust
fn main() {
    let mut count = 0;

    let result = loop {
        count += 1;
        if count > 5 {
            break count * 2;
        }
    };
    println!("Result: {}", result);
}
```

使用**循环标签**来中断外部循环

```rust
fn main() {
    'outer: loop {
        println!("Entered outer loop");
        'inner: loop {
            println!("Entered inner loop");
            break 'outer;
        }
        println!("This point will never be reached");
    }
    println!("Exited outer loop");
}
```

### while 条件循环

程序通常需要评估循环内的条件。当条件为 `true` 时，循环运行。当条件不再为 `true` 时，程序将停止循环

```rust
fn main() {
    let mut count = 0;
    while count < 5 {
        count += 1;
        println!("Count: {}", count);
    }
    println!("Done!");
}
```

### for 遍历循环

`for` 循环用于遍历集合，例如数组、向量、范围等

```rust
fn main() {
    let fruits = ["apple", "banana", "cherry"];

    for fruit in fruits {
        println!("I like {}.", fruit);
    }
}
```

`for` 循环也可以用于遍历数字范围

```rust
fn main() {
    for number in 1..6 {    // 6 不会被取到
        println!("Number: {}", number);
    }
  
    for number in 1..=6 {   // 6 会被取到
        println!("Number: {}", number);
    }
}
```
