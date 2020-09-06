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
- 泛型有子类型化（ subtyping ）的规则，List<String ＞是原生态类型List 的一个子类型，而不是参数化类型List<Object>的子类型（详见第28 条）
- 如果要使用泛型，但不确定或者不关心实际的类型参数，就可以用一个问号代替。例如，泛型Set<E ＞的无限制通配符类型为Set <?>（读作“某个类型的集合”） 。
- 无限制通配类型Set ＜？＞和原生态类型Set 之间有什么区别呢？这个问号真正起到作用了吗？这一点不需要赘述，但通配符类型是安全的，原生态类型则不安全。由于可以将任何元素放进使用原生态类型的集合中，因此很容易破坏该集合的类型约束条件（如之前范例中所示的u 口saf eAdd 方法）；但不能将任何元素（除了null 之外）放到c。llection < ?>中。如果尝试这么做，将会产生一条像这样的编译时错误消息：error: incompatibl e types: String can not be converted to CAP
- 必须在类文字（ class l i te ra l ） 中使用原生态类型。规范不允许使用参数化类型（虽然允许数组类型和基本类型）［ JLS, 15.8.2 ］ 。换句话说， List.class 、Stri 呵［］ . class 和int . class 都合法，但是L i st<String .class 和List<?>.class 则不合法。
- 由于泛型信息可以在运行时被擦除，因此在参数化类型而非无限制通配柯：类型上使用instanceof 操作符是非法的
- II Legitima t e use of raw type - instanceof operator if (o i nstanceof Set) { II Raw t ype Set<?> s = (Set<?>) o; I I Wi l dca 「d type 注意，一旦确定这个o 是个Set ，就必须将它转换成通配符类型Set ＜？＞，而不是转 换成原生态类型Set 。这是个受检的（ checked ）转换，因此不会导致编译时警告。
- 原生态类型只是为了与引人泛型之前的遗留代码进行兼容和互用而提供的。让我们做个快速的回顾：Set<Object ＞是个参数化类型，表示可以包含任何对象类型的一个集合； Set ＜？＞则是一个通配符类型，表示只能包含某种未知对象类型的一个集合； Set 是一个原生态类型，它脱离了泛型系统。前两种是安全的，最后一种不安全。