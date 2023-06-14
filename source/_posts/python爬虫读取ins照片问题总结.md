---
title: python爬虫读取ins照片问题总结
date: 2021-03-16
tags: [python]
categories: [编程, bug]
---

在使用 python 爬取 ins 照片时遇到的一些问题

<!--more-->

<img src="https://ydw6tr-blog.oss.laf.run/post/2021-03-28-01.png" align="left">
<div style="clear: both;"></div>
出现该报错时添加cookies

<img src="https://ydw6tr-blog.oss.laf.run/post/2021-03-28-02.png" align="left">
<div style="clear: both;"></div>
这是库ulllib3版本的错误。使用pip install urllib3==1.25.8，降低urllib3的版本
但安装时出现报错

```js
ERROR: Could not find a version that satisfies the requirement urllib3
ERROR: No matching distribution found for urllib3
```

**解决方法:**
因为 python 国内网站网络不稳定的问题，于是使用镜像

```js
pip install 包的名字 -i http://pypi.doubanio.com/simple/ --trusted-host pypi.doubanio.com
```
