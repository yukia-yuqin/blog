---
layout: post
title: C++总结
tags: interview c++
categories: interview
---

CPP<br>
<br>

### 真题
    - 腾讯实习生 一面&二面 后台研发 现场面
        - 自我介绍，然后问memcpy和memmove的区别，剖析性能差异
        - 叙述一下static对变量、对函数、对内函数内部的变量的各种使用的区别
        - 画一下类的对象的内存布局 *
        - PCB内存布局
        - 叙述一下洗牌算法
        - 对系统编程有什么了解的
            - 简述了一下IPC的管道、消息队列、共享内存、信号、线程的基本概念
        - 详细剖析一下四次挥手
        - 解释一下 Python 的装饰器
            - use_logging 就是一个装饰器，它一个普通的函数，它把执行真正业务逻辑的函数 func 包裹在其中，看起来像 foo 被 use_logging 装饰了一样，use_logging 返回的也是一个函数，这个函数的名字叫 wrapper。在这个例子中，函数进入和退出时 ，被称为一个横切面，这种编程方式被称为面向切面的编程。
        - 解释一下 函数重载 是怎么实现的
            - 编译器在汇编层结合函数名和参数类型给重载等函数不同的汇编实现。
            - C/C++ 时混编要使用extern告诉编译器这是不支持重载的C的代码
        - 解释一下函数调用是怎么样的过程（怎么传參）
            - 简述函数栈帧图，即使用两个寄存器分别指向栈底(ebp)与栈顶(esp)，通过ebp +— n访问变量or回到上一个栈帧
            - ebp-4放置了之前栈帧的返回地址，ebp到目标地址之间都是压入的参数
        - 解释一下函数调用，比如 求最大值函数 和 fork/exec 函数有什么区别
            - 前者在用户态完成操作，后者由于权限问题，需要在内核态由内核完成
        - 编程题第一道 string类的实现
    - 阿里 实习生一面 电话面 后台研发
        - 问的超级细，除了网络编程自己不熟悉，该问的全问了，列举部分知识点如下
        - 联合 说明联合共用内存的概念，举例大小端的应用
        -  多态的实现
        - 讲一下函数栈帧 说明函数调用的过程（ebp，esp）
        - 如何使用c实现c++的特性
        - 讲一下哈夫曼动态压缩的详细过程
        - 讲一下泛型编程
        - 讲一下预处理到链接到全过程
        - 讲一下STL库常用的接口
        - 讲一下系统编程
        - 讲一下有名管道
        - 讲一下四次挥手
        - 讲一下NAT协议


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
