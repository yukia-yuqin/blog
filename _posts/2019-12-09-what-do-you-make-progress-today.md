---
layout: post
title: 今天专业技能有没有增长？时习之
tags: study
categories: dailystudy
---

你今天学到了什么<b>专业知识</b>？since 20191108<br>
## 2019-12-08 周日
- 毕设用整数规划

## 2019-12-07 周六
- 网联在用dubbo

## 2019-11-27 周三
- 通信  802.11协议的衰减模型[802.11协议的衰减模型]。综上所述，所以802.11不仅定义了不同场景下的信道模型，也根据发送和接收者距离，分别给出了在视距范围内和外的衰减结果。在基本信道模型给定以后，我们可以从理论上去计算一个实际Wi-Fi节点的传输范围，以后我们再具体进行阐述。

## 2019-11-24 周日
- volatile是java虚拟机提供的轻量级的同步机制：保证可见性(立即斜晖主内存)，不保证原子性(i++是三步操作)，禁止指令重排序。
- JMM是java内存模型，是一个标准，具有可见性，原子性，有序性

## 2019011-22 周五
- 多维数组在内存中存储的模样

## 2019-11-21 周四
- cpu以时间片处理线程，线程切换的时候需要切换上下文（pc,sp）
- cas锁是硬件实现的，ABA问题通过加标号实现。
- synchronized 是悲观锁，JVM的内置锁，由内部对象monitor，cas是乐观锁。
- 对象的实例存储在堆空间，对象的元数据存储在方法区，对象的引用存储在栈空间。
- jvm的运行时数据区有方法区和堆，这两个线程共享，而虚拟机栈，本地方法站，程序计数器是线程私有的。

## 2019-11-20 周三
- thread.join() “等待该线程终止。”
- static

## 2019-11-15 周五
- nothing 

## 2019-11-14 周四
- 今天啥也没学，收到了intel的offer call.

## 2019-11-13 周三
- C++的多线程和多进程，最主要的区别是多线程是有自己的寄存器，有pc和sp(stack pointer), 而多进程是所有的内容都分离。[同步方法][线程进程同步方法]
- this is a test.

## 2019-11-12 周二
- C++的mutex类，有两个方法，Lock unlock，是<b>互斥锁</b>。只能有一个线程得到它。

## 2019-11-11
- 全组合的方法dfs。leetcode1256题花花酱

## 2019-11-10
- VOS
- FEELVOS: Fast End-to-End Embedding Learning for Video Object Segmentation (CVPR 2019)

## 2019-11-09
- 明天想复习一下C++基础知识 2019-11-08 20:59:41
- 访问控制符
- 多线程
- emplace_back。直接在目标内存空间生成对象。无需拷贝。
- vs中debug模式通常关闭了optimization。release模式开启Optimization.
- hh,找到cherno这个人在Youtube上讲的C++，挺好的。
- A.CPP B.CPP--编译-- A.OBJ B.OBJ -- 链接 -- C.exe
- vs中的property:
    - C++有个Preprocess to a file，它可以把preprocess的结果输出到 .i 文件中。源文件加预处理后的文件。
    - C++的output files中有个assemble files会生成.asm文件。汇编语言文件
    - optimization选择optimization，maximize speed， 并且在code generation中选择basic runtime checks为default.会使asm文件小得多。
    - Linker->advanced->entry point.可以不是main的函数。
- error: c2010这种以c开头的是compiler error. lnk开头的是link error。
- static关键字表明该函数只在当前文件下起作用。extern。
- class默认是private的，struct默认是public的。
- C++中基本变量是不会被自动设置为0的，跟JAVA中不一样。

## 2019-11-08
- multiset是有序的,key可重复的
- emplace 最大的作用是避免产生不必要的临时变量，因为它可以完成 in place 的构 造(http://blog.guorongfei.com/2016/03/16/cppx-stdlib-empalce/)


[线程进程同步方法]:https://photos.google.com/share/AF1QipMMoeW8JX5fmSa9rSrC0Cmmq_OnpAMu6hSbuWiaQ8An5cqRz5MtJ6FzJPQZQMGFbQ/photo/AF1QipPRxqN6NFYMJM9kSIhohiIdF8wPESTOihbqdM5h?key=Nm90SEpvY2YtcXlmanhxM1p0SThoc3lRZVdrX1Rn
[802.11协议的衰减模型]https://zhuanlan.zhihu.com/p/24349070