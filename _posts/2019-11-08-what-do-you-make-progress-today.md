---
layout: post
title: 今天专业技能有没有增长？时习之
tags: study
categories: dailystudy
---

你今天学到了什么<b>专业知识</b>？since 20191108<br>
## 2019-11-15 周五
- nothing

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