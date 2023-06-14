---
title: npm install报错
tags: [npm]
categories: [编程, bug]
date: 2021-03-16
---

在前端项目里安装安装 gulp 的时候，出现了如下 "Sorry, name can only contain URL-friendly characters."

<!--more-->

<img src="https://ydw6tr-blog.oss.laf.run/post/2021-03-16-01.png" align="left">
<div style="clear: both;"></div>

这是因为在 npm 初始化的时候，会向我们询问项目名，如果我们不命名回车跳过的话，它会指定你的文件件的名称当做项目名。但是我的项目名称是不规范的有了两个-，所以需要重新**npm install gulp --save-dev**一下，在询问项目名的时候定义一下，比如说 police。然后其他的信息可以先不填后期填。

 <img src="https://ydw6tr-blog.oss.laf.run/post/2021-03-16-02.png" align="left">
 <div style="clear: both;"></div>
 
 最后确认
 <img src="https://ydw6tr-blog.oss.laf.run/post/2021-03-16-03.png" align="left">
 <div style="clear: both;"></div>
