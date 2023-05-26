---
title: github page+hexo 绑定域名后页面显示404
tags: [github]
categories: [编程, bug]
date: 2023-05-25 17:20:04
---

github page + hexo 搭建个人博客，绑定域名后正常访问。等在添加新文章后访问变 404

<!--more-->

### 原因

上传新文件后，actions 重新部署项目，导致域名配置的 CNAME 文件被删了。

### 解决方法

在 GitHub 项目中的 Settings->Pages 下的 Custom domain 重新填入自定义域名，重新生成 CNAME 文件后，网站恢复正常访问
