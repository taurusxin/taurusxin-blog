---
title: "本站已接入 HTTP3/QUIC"
categories: [ "前沿技术探索" ]
tags: [ "http3" ]
draft: false
slug: "http3-enabled"
date: "2021-03-14 12:32:00"
---

在去年的时候，本站正式接入了TLS1.3，使得TLS握手更快，从而加快体验。

2020年10月，Google 正式宣布 Chrome 将支持 HTTP3

在最2021年的网站升级中，本站正式支持了 HTTP3。

Chrome 启用 HTTP3 方法，在chrome地址栏输入`chrome://flags`，搜索`Experimental QUIC protocol`

如下图，将 `default` 改为 `enable` 即可。

![Chrome 开启 QUIC 设置](https://cdn.taurusxin.com/hugo/2024/08/06/chrome.png)

多刷新几次页面后，就可以看到浏览器已经使用 h3 协议进行数据传输了。

![博客启用 HTTP/3](https://cdn.taurusxin.com/hugo/2024/08/06/blog-http3.png)

#### 后言

因为国内运营商对于UDP支持欠佳，所以目前 HTTP/3 只是在实践过程中，期待以后的表现。
