---
title: Java JFileChooser保存文件
tags: [java]
categories: [编程]
date: 2020-06-08
---

如何使用 JFileChooser 保存文件

<!--more-->

> 原文链接: [JFileChooser 保存文件](https://zhidao.baidu.com/question/202631853.html)

```js
//创建文件选择器
JFileChooser fileChooser = new JFileChooser();
//后缀名过滤器
FileNameExtensionFilter filter = new FileNameExtensionFilter("标签文件(*.txt)", "txt");
fileChooser.setFileFilter(filter);
// 在容器上打开文件选择器
fileChooser.showSaveDialog(jf);
File f=fileChooser.getSelectedFile();
//字节输出流
FileOutputStream fos = null;
	try {
			String fname = f.getName();//从文件名输入框中获取文件名
			//创建文件
			File file=new File(fileChooser.getCurrentDirectory()+"/"+fname+".txt");
			fos = new FileOutputStream(file);
			//写入文件操作
			String Datas = proDatas.toString();
			fos.write(Datas.getBytes());
			fos.close();

		} catch (IOException e1) {
					System.err.println("IO异常");
					e1.printStackTrace();
				}
```

关于从文件输入框获取文件名时，使用 fileChooser.getSelectedFile().getName()。但我们是”保存“，并没有选择文件。关于这一点，我引用大佬的解释：

```markdown
1、JFileChooser.getSelectedFile()返回一个文件 bai 对象，调这个文件对象的 dugetName()很容易得到用户输入的 zhi 文件名。返回文 dao 件对象既包含了文件路径也包含了文件名，这也体现了 Java 面向对象的思想。

2、Java 的文件对象在文件系统中是可以存在，也可不存在的，所以 Java 的文件对象有 exists()、createNewFile()、mkdir()等方法。所以文件保存对话框返回的文件对象不一定在文件系统实际存在，而仅仅是一串路径的表示。
```
