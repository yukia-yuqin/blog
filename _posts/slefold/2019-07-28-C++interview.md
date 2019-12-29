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
            - [leetcode 原题]
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
    - C++11新特性
        - int* xx= new int[3]{ 1,2,3 }; 允许new带初始化；
        - auto关键字。在C++11之前，auto关键字用来指定存储期。在新标准中，它的功能变为类型推断。auto现在成了一个类型的占位符，通知编译器去根据初始化代码推断所声明变量的真实类型。各种作用域内声明变量都可以用到它。例如，名空间中，程序块中，或是for循环的初始化语句中。


    - 引用和指针
        - 引用没有内存空间，指针有内存空间
        - 指针有内存空间，在申明的时候可以不初始化，可以指向任何同类型的地址空间，可以当成一个数组的对象，引用没有内存空间，不是一个普通的变量。引用没有内存空间，初始化之后不能被赋值，不能组成一个数组。可以有指针数组，但不能有引用数组。
        - 引用的类型是它代表的对象的类型，而不是一个指针，因而delete的时候不能删除。
        - 引用是一个只读指针。
        - 这是C++语义的定义，在gcc4.8里面，引用也是有内存空间的，引用也是可以赋值的，
        - 数组名就是一个引用。(不能被赋值，取地址就是数组对象的地址，没有自己的地址空间)
    - 疑问：
        - 不能返回函数内部new分配的内存的引用。这条可以参照Effective C++[1]的Item 31。虽然不存在局部变量的被动销毁问题，可对于这种情况（返回函数内部new分配内存的引用），又面临其它尴尬局面。例如，被函数返回的引用只是作为一个临时变量出现，而没有被赋予一个实际的变量，那么这个引用所指向的空间（由new分配）就无法释放，造成memory leak。

        - int  a=4;
            int  &f(int x)
            {    a=a+x;
                return a;
            }

            int main()
            {
                int t=5;
                cout<<f(t)<<endl;	//a = 9
                f(t)=20;	// a = 20;
                cout<<f(t)<<endl;	//25
                t=f(t);	
                cout<<f(t)<<endl;	//t = 60
            }
    - 纯虚函数
        定义一个函数为虚函数，不代表函数为不被实现的函数。
        定义他为虚函数是为了允许用基类的指针来调用子类的这个函数。
        定义一个函数为纯虚函数，才代表函数没有被实现。
    - 左值和右值
        - 在C++11中所有的值必属于左值、右值两者之一，右值又可以细分为纯右值、将亡值。在C++11中可以取地址的、有名字的就是左值，反之，不能取地址的、没有名字的就是右值（将亡值或纯右值）。举个例子，int a = b+c, a 就是左值，其有变量名为a，通过&a可以获取该变量的地址；表达式b+c、函数int func()的返回值是右值，在其被赋值给某一变量前，我们不能通过变量名找到它，＆(b+c)这样的操作则不会通过编译。
    - 讲得好 https://bestmind.space/posts/%E5%B8%B8%E8%A7%81C-%E9%9D%A2%E8%AF%95%E9%A2%98/

### 基础 🤣🤣
    - 
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
    - rand() 产生的随机数在每次运行的时候都是与上一次相同的。若要不同, 用函数 srand() 初始化它。可以利用 srand((unsigned int)(time(NULL)) 的方法，产生不同的随机数种子，因为每一次运行程序的时间是不同的。

- 百度智能云面试
    - time_wait状态产生的原因，危害，如何避免 https://blog.csdn.net/weibo1230123/article/details/81950420
    - 用shell写一个查找文件中包含某个字符的行的最后一列，然后统计
        - https://www.ibm.com/developerworks/cn/linux/l-cn-awk-httplog/index.html awk操作行
    



## 2019-11-09-CPP
- include 
    ```
    执行Main.cpp会输出什么？
    文件EndBrace.h:
    }
    文件Main.cpp:
    #include <iostream>
    int main() {
        int a = 2, b = 3;
        int result = a * b;
        std::cout << result << std::endl;
    #include "EndBrace.h"
    \\ ouput: 6
    ```
    
- empalce
    - 考点：vector的长度不够时resize会复制一次 & push_back会在Main中生成一次然后复制到目标vector中 
    ```
    如下代码会输出什么？
    struct Vertex
    {
        float x, y, z;

        Vertex(float x, float y, float z) : x(x), y(y), z(z)
        {
        }

        Vertex(const Vertex& vertex) : x(vertex.x), y(vertex.y), z(vertex.z)
        {
            std::cout << "copied!" << std::endl;
        }
    };

    int main()
    {
        std::vector<Vertex> vertices;
        vertices.push_back({ 1,2,3 });
        vertices.push_back({ 4,5,6 });
        vertices.push_back({ 7,8,9 });
        std::cin.get();
        return 0;
        ////output:
        ////copied!
        ////copied!
        ////copied!
        ////copied!
        ////copied!
        ////copied!

        //case2:
        //std::vector<Vertex> vertices(3); 
        ////output:编译错误：没有合适的默认构造函数可用	
        
        //case3:
        //std::vector<Vertex> vertices;
        //vertices.reserve(3);
        //vertices.push_back({ 1,2,3 });
        //vertices.push_back({ 4,5,6 });
        //vertices.push_back({ 7,8,9 });
        //std::cin.get();
        //return 0;
        ////output:
        ////copied!
        ////copied!
        ////copied!

        //case4:
        //std::vector<Vertex> vertices;
        //vertices.reserve(3);
        //vertices.emplace_back(1, 2, 3);
        //vertices.emplace_back(4, 5, 6);
        //vertices.emplace_back(7, 8, 9);
        //std::cin.get();
        //return 0;
        //// output: nothing
    }    
    ```




[20道必须掌握的C++面试题](https://m.w3cschool.cn/cpp/cpp-a9no2ppi.html)
