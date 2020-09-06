---
layout: post
title: java
tags: java
categories: java
---

> effective java   java jdk作者

### 对于所有对象的通用方法

- m.put ( new PhoneNumbe（707，867，5309），“jenny”），此时是根据hash值来进行存储到散列桶的，因此需要重写hashCode的方法。
- 在实际应用中， toString 方法应该返回对象中包含的所有值得关注的信息，、
- 事实上，实现Cloneable 接口的类是为了提供一个功能适当的公有的cl 。ne 方法。为了达到这个目的，类及其所有超类都必须遵守一个相当复杂的、
  不可实施的，并且基本上没有文档说明的协议。由此得到一种语言之外的（ extralinguistic)机制：它无须调用构造器就可以创建对象。
- 因为Java 支持协变返回类型（ covariant return type ） 。换句话说，目前覆盖方法的返回类型可以是被覆盖方法的返回类型的子类了。、
- 这是个根本的问题： 就像序列化一样， Cloneable 架构与引用可变对象的final 域的正常用法是不相兼容的，