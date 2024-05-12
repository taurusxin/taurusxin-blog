---
title: "「小工具」知名屏保 Fliqlo 1.5 修改版（修复黑屏等问题）"
categories: [ "程序人生", "前端技术" ]
tags: [ "fliqlo", "scr", "screensaver" ]
draft: false
slug: "fliqlo-domestic"
date: "2024-05-12T19:46:00+0800"
---

## Fliqlo

Fliqlo 是一款知名的屏保软件，它模拟了一个数字时钟，看起来非常的简洁和美观。但是，Fliqlo 1.5 版本在 Windows 10/11 下会出现黑屏等问题，这里提供了一个修改版，修复了这些问题。

![Fliqlo 屏保](https://cdn.taurusxin.com/hugo/2024/05/12/fliqlo.png)

## 为啥要修改

Fliqlo 1.5 版本在 Windows 10/11 下会出现黑屏等问题，在 1.4 版本之后，将原先使用 Flash 技术改成了用 C# 重新编写，套用了 Webbrowser 控件，访问了一个在线的 HTML 页面，但因为国内访问这个网站的速度太慢，导致了黑屏等问题，其实是网页根本没有加载出来。

![Fliqlo 的部分源代码](https://cdn.taurusxin.com/hugo/2024/05/12/fliqlo-source.png)

我将这个网页进行了一部分逆向，并且部署到我的服务器（fliqlo.taurusxin.com）解决了这个问题，现在你如果使用我的版本，那么载入速度将会变得特别快且不会再黑屏。

## 下载

- [Fliqlo 1.5 修改版](https://cdn.taurusxin.com/hugo/2024/05/12/Fliqlo1.5.zip)
