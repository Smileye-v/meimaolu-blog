---
title: Mysql错误提示
tags: [mysql]
categories: [编程, bug]
date: 2020-11-17
---

Mysql 错误提示 Can‘t create table, errno:165

 <!--more-->

去掉 my.ini 里面的 innodb_force_recovery = 4 然后重新启动 mysql 服务
