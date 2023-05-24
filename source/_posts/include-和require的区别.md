---
title: include 和require的区别
tags: [php]
categories: [编程, php]
date: 2019-04-17
---

require 和 include 都是引入文件，有什么区别呢？

<!--more-->

# include 和 require 的区别

### 前言

require 和 include 都是引入文件，有什么区别呢？

### require

require 这个函数通常放在 PHP 程序的最前面，PHP 程序在执行前，就会先读入 require 所指定引入的文件，使它变成 PHP 程序网页的一部份。常用的函数，亦可以这个方法将它引入网页中。

### include

include 这个函数一般是放在流程控制的处理部分中。PHP 程序网页在读到 include 的文件时，才将它读进来。可以把程序执行时的流程简单化。

### 区别

- Php 在遇到 include 时就解释一次，如果页面中出现 10 次 include ，php 就解释 10 次，而 php 遇到 require 时只解释一次，即使页面出现多次 require 也只解释一次，因此 require 的执行表率比 include 高。
- Php 使用 require 包含文件时将被包含的文件当成当前文件的一个组成部分，如果被包含的文件中有语法错误或者被包含的文件不存在，则 php 脚本将不再执行，并提示错误。

- Php 使用 include 包含文件时相当于指定了这个文件的路径，当被包含的文件有语法错误或者被包含的文件不存在时给出警告，不影响本身脚本的运行。

- Include 在包含文件时可以判断文件是否包含，而 require 则不管任何情况都包含进来。

- Require 的效率比 require_once 的效率更高，因为 require_once 在包含文件时要进行判断文件是否已经被包含。
