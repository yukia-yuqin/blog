---
layout: post
title: C++总结
tags: interview c++
categories: interview
---

CPP<br>
<br>

### 基础
    - [20道必须掌握的C++面试题][20道必须掌握的C++面试题]
    - 迭代器
        - 迭代器是STL的精髓，我们这样描述它：迭代器提供了一种方法，使它能够按照顺序访问某个容器所含的各个元素，但无需暴露该容器的内部结构。它将容器和算法分开，好让这二者独立设计。
    - 指针和引用的区别
        - 指针可以有多级，但是引用只能是一级（int **p；合法 而 int &&a是不合法的）
    - [const](https://github.com/huihut/interview#-cc)
    - static
    - this 指针
    - inline 内联函数
        - 相当于把内联函数里面的内容写在调用内联函数处；
    - volatile
    - assert()
    - #pragma pack(n)
    - 位域
    - extern "C"
    - struct 和 typedef struct
    - C++ 中 struct 和 class
        - 默认的继承访问权限。struct 是 public 的，class 是 private 的。
    - union 联合
    - explicit（显式）关键字
        - explicit 修饰构造函数时，可以防止隐式转换和复制初始化
    - friend 友元类和友元函数
        - 友元关系不可传递；友元关系的单向性
    - using
    - C++ 多态分类及实现：
        - 重载多态（Ad-hoc Polymorphism，编译期）：函数重载、运算符重载
        - 子类型多态（Subtype Polymorphism，运行期）：虚函数
        - 参数多态性（Parametric Polymorphism，编译期）：类模板、函数模板
        - 强制多态（Coercion Polymorphism，编译期/运行期）：基本类型转换、自定义类型转换
    - 虚析构函数;虚析构函数是为了解决基类的指针指向派生类对象，并用基类的指针删除派生类对象。
    - 虚函数、纯虚函数 
    - new、delete,// 先内存分配 ，再构造函数,// 先析构函数，再内存释放
    - 定位 new ; 定位 new（placement new）允许我们向 new 传递额外的地址参数，从而在预先指定的内存区域创建对象。
    - 如何定义一个只能在堆上（栈上）生成对象的类？
    - 智能指针
        - shared_ptr;多个智能指针可以共享同一个对象，对象的最末一个拥有着有责任销毁对象，并清理与该对象相关的所有资源。
        - unique_ptr;weak_ptr;auto_ptr
    - 强制类型转换运算符;static_cast;dynamic_cast;const_cast;reinterpret_cast
    - 宁可以编译器替换预处理器（尽量以 const、enum、inline 替换 #define）
    - 尽可能使用 const
    - 左值右值
        - 其中纯右值的概念等同于我们在C++98标准中右值的概念，指的是临时变量和不跟对象关联的字面量值；将亡值则是C++11新增的跟右值引用相关的表达式，这样表达式通常是将要被移动的对象（移为他用），比如返回右值引用T&&的函数返回值、std::move的返回值，或者转换为T&&的类型转换函数的返回值。
    - && is new in C++11. int&& a means "a" is an r-value reference. && is normally only used to declare a parameter of a function. And it only takes a r-value expression. 
    - 十大必掌握C++11新特性
        - 　　1、新增基于范围的for循环 ；　　2、自动类型推断 auto ；　　3、匿名函数 Lambda ；　　4、后置返回类型（tailng-return-type）
    - C++ STL中的map用红黑树实现，搜索效率是O(lgN),为什么不像python一样用散列表从而获得常数级搜索效率呢？  
        - 是的，所以C++11隆重推出unordered_map，提供类似python字典的功能。从此有序和无序map双剑合璧，可以自主选择。








[20道必须掌握的C++面试题](https://m.w3cschool.cn/cpp/cpp-a9no2ppi.html)
