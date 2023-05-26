---
title: beautyEye输入框中文输入法白屏
tags: [java, beautyEye]
categories: [编程, bug]
date: 2020-05-23
---

在使用 Java Swing 编写程序时引用 beautyEye 以修改样式，但在使用输入框时，输入中文窗口就出现白屏

<!--more-->

<img src="/img/post/2020-05-23-01.png" align="left">
<div style="clear: both;"></div>

<img src="/img/post/2020-05-23-02.png" align="left">
<div style="clear: both;"></div>

# 解决方法：

在初始化前加入 System.setProperty(“sun.java2d.noddraw”, “true”);

```js
public static void main(String[] args) {

		try {
			System.setProperty("sun.java2d.noddraw", "true");
			org.jb2011.lnf.beautyeye.BeautyEyeLNFHelper.launchBeautyEyeLNF();

		} catch (Exception e) {
			// TODO exception
		}

	}
```
