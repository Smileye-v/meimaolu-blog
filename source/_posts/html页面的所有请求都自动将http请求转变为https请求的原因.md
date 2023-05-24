---
title: html页面的所有请求都自动将http请求转变为https请求的原因
date: 2021-04-20 03:08:20
tags: [html, http, https]
categories: [编程, bug]
---

html 在加载静态资源时自动将 http 请求转化为了 https

<!--more-->

**解决方法:**

index.html 头中有如下代码

```
<meta http-equiv=“Content-Security-Policy” content=“upgrade-insecure-requests”>
```

这个代码的作用是将站内加载的资源自动将 http 转为 https
如果不需要去掉就可以解决问题。
