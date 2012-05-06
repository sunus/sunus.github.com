---
title: Java修饰符
layout: post
categories:
- Tech
tags:
- JAVA
- Development
---

刚刚看appfuse的时候看到 private transient ServletContext servletContext; 发现transient这个单词不认识，汗…… 赶紧google，学习了一下，发现除了transient，Java还有几个不大常用的修饰符（至少我不大熟悉） 现学现卖，这里简单介绍一下 

* **native** 使用对象：成员 介绍：与操作平台相关，定义时并不定义其方法，方法的实现被一个外部的库实现，大多数情况下该方法的实现是用C、C++编写的。 
* **strictfp** 使用对象：类、方法 介绍：strictfp修饰的类中所有的方法都隐藏了strictfp修饰词，方法执行的所有浮点计算遵守IEEE 754标准，所有取值包括中间的结果都必须表示为float或double类型，而不能利用由本地平台浮点格式或硬件提供的额外精度或表示范围。 
* **synchronized** 使用对象：方法 介绍：对于一个静态的方法，在执行之前jvm把它所在的类锁定；对于一个非静态类的方法，执行 前把某个特定对象实例锁定。（提供多线程的支持）
* **volatile** 使用对象：字段 介绍：指出可能有多个线程修改此变量，要求编译器优化以保证对此变量的修改能够被正确的处理 
* **transient** 使用对象：字段 介绍：字段不是对象持久状态的一部分，在类对象持久化的时候，此变量不需要持久保存
