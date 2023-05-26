---
title: github actions执行异常
tags: [github]
categories: [编程, bug]
date: 2023-03-20
---

在使用 actions 自动生成 md 文件时异常报错

<!--more-->

### 403 错误

没有相关权限，修改权限为可读写后执行正常

### 401 错误

生成文件设置的 Actions secrets 有效期限到期，更新后正常
