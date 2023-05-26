---
title: Java mousedragged事件时控件闪烁
tags: [java]
categories: [编程, bug]
date: 2020-05-18
---

在使用 Java Swing 做程序时，使用 MouseMotionListener 的 mousedragged 鼠标事件，但拖动时，元素位置闪烁变化

<!--more-->

<img src="/img/post/2020-05-18-01.png" align="left">
<div style="clear: both;"></div>
输出了位置数值查看发现位置会往左上角**“瞬移”**。

```js
import java.awt.event.MouseMotionListener;
```

```js
public void mouseDragged(MouseEvent e) {
//鼠标拖动
	// TODO Auto-generated method stub
    panel_lable.setLocation(e.getX(),e.getY());//面板位置随鼠标拖动变化，
	System.out.println(e.getX()+","+e.getY());
}
```

# 解决方法

因为我用的是 awt 的组件,需要使用双缓冲来避免画面的抖动。修改后的代码如下:

```js
public void mouseDragged(MouseEvent e) {
//鼠标拖动
	// TODO Auto-generated method stub
    panel_lable.setLocation(e.getX()+(int)panel_lable.getLocation().getX(),e.getY()+(int)panel_lable.getLocation().getY());//面板位置随鼠标拖动变化，
	System.out.println(e.getX()+","+e.getY());
}
```

修改后抖动的问题就没有了。
