---
title: "一夜爆火的小工具 - 给你的头像加上圣诞帽"
categories: [ "Tool" ]
tags: [ "头像", "圣诞帽" ]
draft: false
slug: "christmas-hat"
date: "2025-12-08T23:51:00+0800"
---

## 欢迎！

如果你是从我的「圣诞帽🎄 By TaurusXin」站点过来的，那么非常欢迎你也点进了我的博客，这里是我创作和分享灵感与生活日常的地方，希望你能够喜欢这里！

如果你不知道，那么可以[点击这里](https://tools.taurusxin.com/hat/)去看看，这是一个非常有意思的小工具，用于给你的社交媒体头像戴上一顶圣诞帽。

## 起因

12 月 8 日早上，我收到了十几封来自腾讯云 EdgeOne 与 Cloudflare 的邮件，均提示我的 CDN 流量与请求数量异常高，已经接近我设定的阈值上限而被关停。

开始认为是 PCDN 又在刷流量，后面登上 EdgeOne 的控制台发现都是正常的流量访问，来源是遍布全球的地址。

![EdgeOne 控制台](https://cdn.taurusxin.com/hugo/2025/12/08/edgeone.png)

此时 EdgeOne CDN 已经自动关停，而 Cloudflare 也提示我 Worker 与 Pages 的访问数即将达到阈值

![Cloudflare](https://cdn.taurusxin.com/hugo/2025/12/08/image-20251208235559914.png)

## 扩容

到公司后，我立马开始着手流量激增的问题，好在我现在部署的服务器完全能够承载住此次流量，多亏了腾讯云的锐驰服务器。200M的带宽让资源非常轻松地就能够迅速加载。

分析 Nginx 日志后，最高峰的访问次数来到了 8 日的下午 15:25 分左右，此时 HTTPS QPS 来到了近 100 q/s，流量一度在几十分钟内跑满了 200M 的服务器 BGP 带宽。

紧急加上了 Umami 分析，大约一小时后，后台反馈的数据是，大多数的访问来源为 bing 搜索以及 QQ 空间

![Umami 来源域名](https://cdn.taurusxin.com/hugo/2025/12/09/image-20251209000434150.png)


此时 bing 搜索的排名已经来到了相关关键词的第一位。

![Bing 搜索](https://cdn.taurusxin.com/hugo/2025/12/09/image-20251209000227555.png)

## 结语

不管怎么说，这也是我制作的内容第一次出圈，也希望您能喜欢这里！

另外附上项目的开源地址：<https://github.com/taurusxin/ChristmasHat>

有兴趣的可以自己去部署玩一玩！

提前预祝所有阅读到这篇文章的伙伴圣诞快乐！
