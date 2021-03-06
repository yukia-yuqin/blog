---
layout: post
title: java总结
tags: interview java
categories: interview
---

来杯咖啡吧~~<br>
<br>

## java学习大纲
    鲁班学院Java高级课程大纲（VIP）
### 并发编程专题
  -  JAVA内存模型（JMM）
  -  java当中的线程通讯和消息传递
  -  什么是重排序和顺序一致性？Happens-Before？As-If-Serial？
  -  Synchronized的概念和分析
  -  同步、重量级锁以及Synchronized的原理分析
  -  自旋锁、偏向锁、轻量级锁、重量级锁的概念、使用以及如何来优化他们
  -  Volatile和DCL的知识
  -  Volatile的使用场景和Volatile实现机制、内存语义、内存模型
  -  DCL的单例模式，什么是DCL？如何来解决DCL的问题
  -  并发基础之AQS的深度分析
  -  AbstractAueuedSynchronizer同步器的概念、CLH同步队列是什么？
  -  同步状态的获取和释放、线程阻塞和唤醒
  -  Lock和并发常用工具类
  -  java当中的Lock、ReentrantLock、ReentrantReadWriteLock、Condition
  -  java当中的并发工具类CyclicBarrier、CountDownLatch、Semphore
  -  java当中的并发集合类ConcurrentHashMap、ConcurrentLinkedQueue......
  -  原子操作常用知识讲解
  -  基本类型的原子操作比如经典的AtomicBoolean、AtomicLnteger、AtomicLong
  -  数组类型的原子操作代表几个类AtomicIntegerArray、AtomicLongArray、AtomicReferenceArray
  -  引用类型的原子操作的典型AtomicReference、AtomicReferenceFieldUpdater......
  -  CAS的概念和知识、Compare And Swap 以及他的缺陷
  -  线程池和并发并行
  -  Executor、ThreadPoolExecutor、Callable &amp; Future ScheduledExecutorService
  -  ThreadLocal、Fork &amp; Join？什么是并行？线程池如何保证核心线程不被销毁？
### 互联网工程专题
  -  Maven
  -  整体认知maven的体系结构
  -  maven核心命令
  -  maven的pom配置体系
  -  搭建Nexus私服
  -  Git
  -  动手搭建Git客户端与服务端
  -  Git的核心命令
  -  Git企业应用
  -  git的原理，git底层指针介绍
  -  Linux
  -  Linux原理、启动、目录介绍
  -  Linux运维常用命令、Linux用户与权限介绍
  -  shell脚本编写
### 框架和源码应用专题
  -  mybatis应用和源码解析
  -  myBatis应用
  -  mybatis优缺点、spring 与mybatis 集成、mybaits单独使用
  -  Config、Sql配置、Mapper配置、有几种注册mapper的方法，优先级如何？
  -  mybaits的一级缓存、二级缓存、mybatis的二级缓存为什么是鸡肋？
  -  通用mapper的实现、mybaits编写sql语句的三种方式
  -  如何利用mybaits的源码来扩展一个mybaits的插件，比如扩展一个适合你公司的分页插件
  -  Mybatis源码分析
  -  @MapperScan的源码分析？mapperScan如何生效的？
  -  mybatis如何扩展spring的扫描器的、mybatis扫描完之后如何利用FactoryBean的？
  -  mybaits底层如何把一个代理对象放到spring容器中？用到了spring的哪些知识？
  -  mybaits和spring的核心接口ImportBeanDefinitionRegistrar之间千丝万缕的关系
  -  从mybatis来分析mybatis的执行流程、mybaits的sql什么时候缓存的？缓存在哪里？
  -  mybaits当中的方法名为什么需要和mapper当中的id一致？从源码来说明
  -  tomcat源码解析
  -  tomat的总体概述和tomcat的启动流程源码分析
  -  tomcat当中web请求的源码分析？一个http如何请求到tomcat的？tomcat如何处理的？
  -  tomcat的协议分析，从源码来分析tomcat当中的各种详细配置的意义
  -  tomcat和apache、nginx等等主流静态服务器的搭配使用
  -  tomcat的性能调优？生成环境上如何让你的tomcat容器的性能达到最高
  -  spring源码分析
  -  spring-jcl 日志源码分析
  -  spring的基本应用和spring源码的编译
  -  java 混乱的日志系统，Jul、jcl、log4j、slf4j.....
  -  spring4和spring5在日志方面的源码对比
  -  springaop源码分析
  -  AspectJ和springAop，aspectj的静态织入
  -  JDK动态代理的源码分析，JDK是如何操作字节码
  -  spring通过cglib完成AOP，cglib如果完成方法拦截
  -  AnnotationAwareAspectJAutoProxyCreator如何完成代理织入的
  -  springIOC、AOP、MVC源码分析
  -  BeanDefinition的定义，在spring体系当中beanDefinition的和bean的产生过程有什么关系，sping当中的各种BeanDefinition的作用
  -  BeanDefinition有什么作用？如果来改变一个bean的行为、spring当中有哪些扩展点开源来修改beanDefinition
  -  BeanDefinitionRegistry的作用，源码分析、哪些开源框架利用了这个类
  -  BeanNameGenerator如何改变beanName的生成策略、如何自己写一个beanName的生成策略
  -  BeanPostProcessor如何插手bean的实例化过程、经典的应用场景有哪些？spring内部哪里用到了这个接口
  -  BeanFactoryPostProcessor和BeanPostProcessor的区别、经典应用场景、spring内部如何把他应用起来的
  -  BeanDefinitionRegistryPostProcessor和BeanFactoryPostProcessor的关系已经区别，spring底层如何调用他们
  -  ConfigurationClassPostProcessor这个类如何完成bean的扫描，如何完成@Bean的扫描、如何完成对@Import的解析
  -  @Imoprt的三种类型，普通类、配置类、ImportSelector、spring在底层源码当中如何来解析这三种import的
  -  如何利用ImportSelector来完成对spring的扩展？你所用的其他框架或者技术说明地方体现了这个类的使用
  -  @Configuration这注解为什么可以不加？加了和不加的区别，底层为什么使用cglib
  -  @Bean的方法是如何保证单例的？如果不需要单例需要这么配置？为什么需要这么配置
  -  springFacoryBean和BeanFacory的区别，有哪些经典应用场景？spring的factoryMethod的经典应用场景？
  -  ImportBeanDefinitionRegistrar这个接口的作用，其他主流框架如何利用这个类来完成和spring的结合的？
  -  spring是什么时候来执行后置处理器的？有哪些重要的后置处理器，比如CommonAnnotationBeanPostProcessor
  -  CommonAnnotationBeanPostProcessor如何来完成spring初始化方法的回调。spring内部的各种Procesor的作用分别是什么
  -  spring和springBoot当中的各种@Enablexxxx的原理是什么？如何自己实现一个？比如动态开启某某些自定义功能
  -  spring如何来完成bean的循环依赖并且实例化的，什么是spring的IOC容器，怎么通过源码来理解？
  -  其他，比如Bean的实例化过程，源码中的两次gegetSingleton的不同和相比如SpringMvc的源码分析等等......
###  Spring微服务专题
  -  Spring Cloud
  -  Eureka的源码分析服务注册和服务发现以及心跳机制和保护机制，对比eureka与zookeeper，什么是CAP原则？
  -  Ribbon源码分析和客服端负载均衡，客户端负载均衡？服务端负载均衡？ Ribbon核心组件IRule以及重写IRule
  -  Fegin源码分析和声明式服务调用，Fegin负载均衡，Fegin如何与Hystrix结合使用？ 有什么问题？
  -  Hystrix实现服务限流、降级，大型分布式项目服务雪崩如何解决？ 服务熔断到底是什么？一线公司的解决方案
  -  HystrixDoashboard如何实现自定义接口降级、监控数据、数据聚合等等
  -  Zuul统一网关详解、服务路由、过滤器使用等，从源头来拦截掉一些不良请求
  -  分布式配置中心Config详解，如何与github或是其他自定义的git平台结合、比如gitlab
  -  分布式链路跟踪详解，串联调用链，,让Bug无处可藏，如何厘清微服务之间的依赖关系？如何跟踪业务流的处理顺序？
  -  Spring Boot
  -  Spring Boot的源码分析和基本应用、利用springmvc的知识模拟和手写一个springboot
  -  springmvc的零配置如何实现的？利用servelt3.0的哪些新知识？在springmvc中如何内嵌一个tomcat，如何把web.xml去掉
  -  springboot当中的监听器和设计模式中观察者模式的关系、模拟java当中的事件驱动编程模型
  -  springboot的启动流程分析、springboot如何初始化spring的context？如何初始化DispacterServlet的、如何启动tomcat的
  -  springboot的配置文件类型、配置文件的语法、配置文件的加载顺序、模拟springboot的自动配置
  -  springboot的日志系统、springboot如何设计他的日志系统的，有什么优势？如何做到统一日志的？
  -  Docker
  -  什么是Docker、为什么要使用他、和开发有什么关系？能否带来便捷、Docker 简介、入门，Docker的架构是怎样的？
  -  Docker的三大核心概念：镜像（Images）、容器（Containers）、仓库服务注册器（Registry）他们分别是什么？
  -  Docker的基础用法以及Docker镜像的基本操作
  -  容器技术入门、Docker容器基本操作、容器虚拟化网络概述以及Docker的容器网络是怎样的？
  -  程序员如何利用Dockerfile格式、Dockerfile命令以及docker build构建镜像
  -  Compose和Dockerfile的区别是什么？Compose的配置文件以及使用Compose运行容器、Docker的实战应用
###  分布式专题
  -  分布式协调框架(Zookeeper)
  -  什么是分布式系统？分布式系统有何挑战？Zookeeper快速入门&amp;集群搭建基本使用
  -  Zookeeper有哪些常用命令以及注意事项、zkclient客户端与curator框架有什么功能以及如何使用
  -  手写Zookeeper常见应用场景：分布式配置中心、分布式锁、分布式定时任务
  -  Zookeeper核心概念znode、watch机制、序列化、持久化机制讲解及其源码解析
  -  Zookeeper怎么解决分布式中的一致性问题？领导选举流程讲解及其源码解析
  -  RPC服务框架(Dubbo)
  -  手写RPC框架以及为什么要使用Dubbo? 传统应用系统如何演变成分布式系统详解
  -  Dubbo的六大特性是什么？对企业级开发有何好处？Dubbo的作用简要说明、快速演示Dubbo调用示例
  -  Dubbo中协议、注册中心、动态代理机制是怎么达到可扩展的？Dubbo的扩展机制源码解析
  -  Dubbo从服务提供者到注册中心到消费者调用服务中间的流程源码解析
  -  Dubbo的监控中心以及管理平台的使用，方便企业级开发与管理
  -  分布式数据缓存(Redis)
  -  关系型数据库瓶颈与优化、ehcache和redis的对比？nosql的使用场景
  -  Redis基本数据类型、比如map的使用场景？有什么优缺点？什么时候用map等等
  -  Redis高级特性、如何来理解redis的单线程但是高性能？如何理解redis和epoll
  -  Redis持久化、什么情况下需要持久化？方案是什么？有什么优缺点？如何优雅的选择持久化方案
  -  Redis项目中应用、reids的高级命令mget、scan？为什么有scan这条命令，如何理解redis的游标？
  -  Redis分布式集群
  -  单机版redis的安装以及redis生产环境启动方案
  -  redis持久化机对于生产环境中的灾难恢复的意义
  -  redis主从架构下如何才能做到99.99%的高可用性
  -  在项目中重新搭建一套主从复制+高可用+多master的redis cluster集群
  -  redis在实践中的一些常见问题以及优化思路（包含linux内核参数优化）
  -  redis的RDB持久化配置以及数据恢复实验
  -  redis的RDB和AOF两种持久化机制的优劣势对比
  -  分布式数据存储(mycat)
  -  分库分表场景介绍
  -  Mycat原理解析
  -  分库分表实战
  -  分布式Rabbitmq
  -  RabbitMQ环境安装&amp;RabbitMQ整体架构与消息流转&amp;交换机详解
  -  消息如何保障 100% 的投递成功方案&amp;企业消息幂等性概念及业界主流解决方案
  -  Confirm确认消息详解&amp;Return返回消息详解&amp;消费端的限流策略&amp;消费端ACK与重回队列机制
  -  SpringAMQP用户管理组件-RabbitAdmin应用&amp;SpringAMQP消息模板组件-RabbitTemplate实战
  -  SpringAMQP消息容器-SimpleMessageListenerContainer详解&amp;SpringAMQP消息适配器-MessageListenerAdapter使用
  -  RabbitMQ与SpringBoot2.0整合实战&amp;RabbitMQ与Spring Cloud Stream整合实战
  -  RabbitMQ集群架构模式&amp;RabbitMQ集群镜像队列构建实现可靠性存储&amp;RabbitMQ集群整合负载均衡基础组件HaProxy_
  -  分布式netty
  -  netty的整体架构实现、netty的模块分析、netty对于大数据的传输、压缩和解压缩
  -  netty的HTTP支持、netty如何实现tomcat的web容器功能、netty对socket的实现
  -  netty和RPC的原理分析、netty和websocket的原理分析、生命周期的理解、服务端怎么实现的
  -  RPC框架分析、什么是RPC，主流RPC框架的使用和原理分析、如何实现自己的RPC框架
  -  netty当中的IO模型分析、NIO的在netty当中的体现、nio的Scattering和Gathering的原理分析
  -  NIO的重要API讲解、NIO的模型原理、NIO的零copy如何实现的、NIO的buffer和channel的应用和原理
  -  selector的源码深入分析、nio的网络编程、nio的堆外内存使用，文件通道的深入使用和理解
  -  netty复合缓冲和其他缓冲的原理分析和各自的使用场景、计数原子和AtomicIntegerFieldUpdater
  -  如何利用nett来实现一个高性能的弹幕系统、比如利用netty模拟实现一个斗鱼的弹幕功能
  -  netty初始化流程总结及Channel与ChannelHandlerContext、channel注册的原理、channel选择器工厂和轮询算法及注册底层实现
  -  netty的线程模型解析、netty的编码解码框架解析、netty自定义协议和TCP粘包拆包的问题如何解决
  -  性能调优
  -  mysql性能调优
  -  mysql中为什么不使用其他数据结构而就用B+树作为索引的数据结构
  -  mysql执行计划详解&amp;mysql查询优化器详解
  -  mysql索引优化实战，包括普通查询、group by、order by
  -  java数据结构算法
  -  hash算法详解、java当中hashmap源码解析、手写一个hashmap
  -  从源码理解hashmapJDK7和JDK8的变化、为什么有这样的变化，Java8新特性
  -  顺序存储、双向链表、单向链表、java当中linkedList的源码分析
  -  java当中线性结构、树形结构以及图形结构分析以及应用场景和经典使用
  -  大数字运算和经典排序、二叉树红黑树排序、查找
  -  JVM性能调优
  -  java内存模型总体概述、类加载过程和classloader、运行时数据区当中的总体内容、编译原理
  -  内存区域与内存溢出异常、虚拟机对象、程序计数器、java栈、本地方法栈、操作数、方法区、堆内存和元数据等等
  -  Classloader的知识详细、默认全盘负责机制、从JDK源码来理解双亲委派模式、如何打破双亲委派？为什么需要打破？
  -  虚拟机性能监控与故障处理、jvm基本命令，jinfo命令的使用jmap命令使用、jstak命令的使用、使用jvisualvm分析
  -  垃圾收集器与内存分配策略、垃圾回收算法与基础、串型收集器、并行收集器、内存分配与回收策略、
  -  程序编译与代码优化、运行期优化、编译期优化、JVM调优的本质是什么？什么是轻gc？什么是Full gc？如何调优
  -  JVM执行子系统、类文件结构、类加载机制、字节码执行引擎、字节码编译模式、如何改变字节码编译模式？
###  项目实战专题
  -  大型互联网电商项目
  -  面试题详解,offer选择
  -  简历技术优化、项目优化
  -  面试问题剖析
  -  职业生涯规划
  -  从原来来说明mybaits的一级缓存为什么会失效？spring为什么把他失效？有没有办法解决？
  -  自由主题


###真题
- 自己的面试的真题
- 4、面试内容
    - 考察内容会相对偏基础，给大家一个参考范围（不限于以下内容）：
    - 1）基础知识
    - 算法与数据结构（可能有在线编程1-2道，难度是 easy middle 之间）：排序算法，简单的二叉树，大数相关
    - 操作系统与网络：多线程与多进程，内存分页，磁盘管理，死锁及如何避免，http(s)协议的安全性，tcp三次握手与可靠传输
    - 数据库：乐观锁与悲观锁，数据库索引的底层数据结构，数据库的原子性
    - 2）编程语言（Java为例）：HashMap扩容、一致性hash，ConcurrentHashMap，GC原理，Integer与int差别，设计模型（单例、工厂等），NIO等
    - 3）项目经验：描述清楚项目背景，项目的实现与技术难点，自己在项目中的贡献，上述也适用于论文
    - 4）开放题：一般在最后两轮面试会有，主要考察理解能力和反应能力
- 二面也是技术面，对简历里面的项目再总结一下哈，可以说清楚项目的意义、如何做、碰到的问题与解决方法；再就是一些基础相关的，可以理解原理并思考原因
    - python 的 id, 垃圾回收(引用计数，标记清除)，深拷贝浅拷贝， == 和 is 哪个是地址那个是内容
    - java 的 i++ 具体是怎么操作的， sycronized 和 violate的区别，抽象和接口的区别
    - spark 的 namenode 和 datanode 的 区别，窄依赖和宽依赖的区别
    - token https://yq.aliyun.com/articles/594217

- 网络相关
    - https的加密方式，原理
        - [如何保证客户端收到的证书是服务器下发的证书，没有被中间人篡改过 https://zhuanlan.zhihu.com/p/25976060 
            - 用公钥解密并验证数字签名
            - 数字证书本身已经提供方案了，数字证书中除了包含加密之后的服务器公钥，权威机构的信息之外，还包含了证书内容的签名(先通过Hash函数计算得到证书数字摘要，然后用权威机构私钥加密数字摘要得到数字签名)，签名计算方法以及证书对应的域名。
        - https发送的详细包过程 https://zhuanlan.zhihu.com/p/25030869 更详细的 http://www.moserware.com/2009/06/first-few-milliseconds-of-https.html
        - ssh(和https的不同？) https://blog.csdn.net/liubo2012/article/details/8894143 
        - 加密算法 https://zhuanlan.zhihu.com/p/27395037 
        - http缺点 http://cycle263.github.io/blogs/http/articles/https.html
        - HTTPS 协议（HyperText Transfer Protocol over Secure Socket Layer）：可以理解为HTTP+SSL/TLS， 即 HTTP 下加入 SSL 层，HTTPS 的安全基础是 SSL，因此加
        - 使用了对称加密+非对称加密（交换密钥）+CA证书三种方式进行加密
        - https://www.jianshu.com/p/b894a7e1c779
        - 非对称加密。这种加密或许理解起来比较困难，这种加密指的是可以生成一对密钥 (k1, k2)。凡是 k1 加密的数据，k1 自身不能解密，而需要 k2 才能解密；凡是 k2 加密的数据，k2 不能解密，需要 k1 才能解密。这种算法事实上有很多，常用的是 RSA。对称加密AES。
    - tcp三次握手与可靠传输 
        - tcp 头部  https://www.cnblogs.com/li-hao/archive/2011/12/07/2279912.html
            - 有ACK/SYN/PIN/序号/确认序号/窗口大小等内容
        - tcp为什么三次握手和四次挥手 https://juejin.im/post/5b1e9c65f265da6e26099bf3
            - 三次握手可以很好的避免网络超时导致的丢包情况，服务器和客户端都要分别收到正确的ACK之后才能表示连接建立，如果未收到，就会启用超时重传机制。当然如果网络确实比较差，导致连接无法建立，也不可能一直重传。操作系统中会有设置重传次数这个字段，以避免无效重转。
            - 至于为啥是四次挥手，本质的原因是咱们的tcp连接是全双工的，在两个方向都需要关闭，所以两个方向都需要发送一个关闭请求和确认请求。
        - tcp如何保证可靠传输csnote https://cyc2018.github.io/CS-Notes/#/notes/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%20-%20%E4%BC%A0%E8%BE%93%E5%B1%82?id=tcp-%e5%8f%af%e9%9d%a0%e4%bc%a0%e8%be%93
            - 超时重传是TCP协议保证数据可靠性的一个重要机制，其原理是在发送某一个数据以后就开启一个计时器，在一定时间内如果没有得到发送的数据报的ACK报文，那么就重新发送数据，直到发送成功为止。三次握手，正常的数据传输，以及四次握手过程中只要出现超时情况，都会触发重传。
            - 设置重传时间间隔RTO  RTO = RTTs （加权平均往返时间） + 4RTTd（偏差的加权平均值）
    - 讲一下OSI7层模型，传输层是干什么的 csnote https://cyc2018.github.io/CS-Notes/#/notes/%E8%AE%A1%E7%AE%97%E6%9C%BA%E7%BD%91%E7%BB%9C%20-%20%E6%A6%82%E8%BF%B0?id=_2-osi
        - 传输层 ：为进程提供通用数据传输服务。由于应用层协议很多，定义通用的传输层协议就可以支持不断增多的应用层协议。运输层包括两种协议：传输控制协议 TCP，提供面向连接、可靠的数据传输服务，数据单位为报文段；用户数据报协议 UDP，提供无连接、尽最大努力的数据传输服务，数据单位为用户数据报。TCP 主要提供完整性服务，UDP 主要提供及时性服务。
        - https://blog.csdn.net/u011774517/article/details/67631439

    - tcp为什么三次握手和四次挥手
    - 讲一下OSI7层模型，传输层是干什么的 
    - 讲一下URL之后发生了什么
    - 讲一下TCP和UDP的区别
    - TCP握手各个阶段的名字
    - DNS用的什么协议
    - HTTP协议和IP协议
    - TCP 为什么 慢

- java容器
    - ArrayList多线程什么问题
    - hashmap  
        - hashmap是一个数组链表 具体是包含entry数组的table；transient Entry[] table; Entry 存储着键值对。它包含了四个字段 hashcode,key,value,next
        - 链表的插入是以头插法方式进行的.查找计算键值对所在的桶；在链表上顺序查找，时间复杂度显然和链表的长度成正比。
        - hash原理/一致性原理？ 通过移位和异或操作，将高位与地位的特征结合起来降低哈希冲突的概率。 https://www.zhihu.com/question/20733617
        - hashmap如何确定下标：4.1 计算 hash 值 + 扰动 4.2 取模 
        - 扩容-基本原理？使得平均查找次数的复杂度为 O(N/M)。 和扩容相关的参数主要有：capacity-必须保证为 2 的 n 次方、size-键值对数量、threshold-size 的临界值，当 size 大于等于 threshold 就必须进行扩容操作 和 load_factor。HashMap 总是使用2的幂作为哈希表的大小。
        - hash一致性-扩容-重新计算桶下标，？对于一个 Key，它的哈希值如果在第 5 位上为 0，那么取模得到的结果和之前一样；如果为 1，那么得到的结果为原来的结果 +16。
        - 计算数组容量：mask+1 是大于原始数字的最小的 2 的 n 次方。 
        - 与 HashTable 的比较？ HashTable 使用 synchronized 来进行同步。HashMap 可以插入键为 null 的 Entry。HashMap 的迭代器是 fail-fast 迭代器。HashMap 不能保证随着时间的推移 Map 中的元素次序是不变的
        - HashSet 和 HashMap 区别:如果你看过 HashSet 源码的话就应该知道：HashSet 底层就是基于 HashMap 实现的
        - java为数据结构中的映射定义了一个接口java.util.Map;它有四个实现类,分别是HashMap Hashtable LinkedHashMap 和TreeMap. 
        - Hashmap 是一个最常用的Map,它根据键的HashCode值存储数据,根据键可以直接获取它的值，具有很快的访问速度，遍历时，取得数据的顺序是完全随机的。 HashMap最多只允许一条记录的键为Null;允许多条记录的值为 Null;HashMap不支持线程的同步，即任一时刻可以有多个线程同时写HashMap;可能会导致数据的不一致。如果需要同步，可以用 Collections的synchronizedMap方法使HashMap具有同步的能力，或者使用ConcurrentHashMap。
        - Hashtable与 HashMap类似,它继承自Dictionary类，不同的是:它不允许记录的键或者值为空;它支持线程的同步，即任一时刻只有一个线程能写Hashtable,因此也导致了 Hashtable在写入时会比较慢。
        - HashMap是一个最常用的Map，它根据键的hashCode值存储数据，根据键可以直接获取它的值，具有很快的访问速度。HashMap最多只允许一条记录的键为NULL，允许多条记录的值为NULL。
        - HashMap不支持线程同步，即任一时刻可以有多个线程同时写HashMap，可能会导致数据的不一致性。如果需要同步，可以用Collections的synchronizedMap方法使HashMap具有同步的能力。
        - Hashtable与HashMap类似，不同的是：它不允许记录的键或者值为空；它支持线程的同步，即任一时刻只有一个线程能写Hashtable，因此也导致了Hashtable在写入时会比较慢。
        - LinkedHashMap保存了记录的插入顺序，在用Iterator遍历LinkedHashMap时，先得到的记录肯定是先插入的。
        在遍历的时候会比HashMap慢.
        - TreeMap能够把它保存的记录根据键排序，默认是按升序排序，也可以指定排序的比较器。当用Iterator遍历TreeMap时，得到的记录是排过序的。
        - HashMap线程安全吗，多线程什么问题
    - concurrenthash在hashmap之上的改变 https://cyc2018.github.io/CS-Notes/#/notes/Java%20%E5%AE%B9%E5%99%A8?id=_1-%e5%ad%98%e5%82%a8%e7%bb%93%e6%9e%84
        -  存储结构 ConcurrentHashMap 和 HashMap 实现上类似，最主要的差别是 ConcurrentHashMap 采用了分段锁（Segment），每个分段锁维护着几个桶（HashEntry），多个线程可以同时访问不同分段锁上的桶，从而使其并发度更高（并发度就是 Segment 的个数）。
        - size 操作。每个 Segment 维护了一个 count 变量来统计该 Segment 中的键值对个数。如果尝试的次数超过 3 次，就需要对每个 Segment 加锁。
        - JDK 1.8 的改动
            - JDK 1.7 使用分段锁机制来实现并发更新操作，核心类为 Segment，它继承自重入锁 ReentrantLock，并发度与 Segment 数量相等。
            - JDK 1.8 使用了 CAS 操作来支持更高的并发度，在 CAS 操作失败时使用内置锁 synchronized。
            - 并且 JDK 1.8 的实现也在链表过长时会转换为红黑树。TreeMap、TreeSet以及JDK1.8之后的HashMap底层都用到了红黑树。红黑树就是为了解决二叉查找树的缺陷，因为二叉查找树在某些情况下会退化成一个线性结构。
        - ConcurrentHashMap
        - ConcurrentHashMap 和 Hashtable 的区别
        - ConcurrentHashMap 和 Hashtable 的区别主要体现在实现线程安全的方式上不同。
        - 底层数据结构： JDK1.7的 ConcurrentHashMap 底层采用 分段的数组+链表 实现，JDK1.8 采用的数据结构跟HashMap1.8的结构一样，数组+链表/红黑二叉树。Hashtable 和 JDK1.8 之前的 HashMap 的底层数据结构类似都是采用 数组+链表 的形式，数组是 HashMap 的主体，链表则是主要为了解决哈希冲突而存在的；
        - 实现线程安全的方式（重要）： ① 在JDK1.7的时候，ConcurrentHashMap（分段锁） 对整个桶数组进行了分割分段(Segment)，每一把锁只锁容器其中一部分数据，多线程访问容器里不同数据段的数据，就不会存在锁竞争，提高并发访问率。（默认分配16个Segment，比Hashtable效率提高16倍。） 到了 JDK1.8 的时候已经摒弃了Segment的概念，而是直接用 Node 数组+链表+红黑树的数据结构来实现，并发控制使用 synchronized 和 CAS 来操作。（JDK1.6以后 对 synchronized锁做了很多优化） 整个看起来就像是优化过且线程安全的 HashMap，虽然在JDK1.8中还能看到 Segment 的数据结构，但是已经简化了属性，只是为了兼容旧版本；② Hashtable(同一把锁)：使用 synchronized 来保证线程安全，效率非常低下。当一个线程访问同步方法时，其他线程也访问同步方法，可能会进入阻塞或轮询状态，如使用 put 添加元素，另一个线程不能使用 put 添加元素，也不能使用 get，竞争会越来越激烈效率越低。
    - 各种锁机制,讲得非常好 https://tech.meituan.com/2018/11/15/java-lock.html
        - Java中，synchronized关键字和Lock的实现类都是悲观锁。
        - 而乐观锁认为自己在使用数据时不会有别的线程修改数据，所以不会添加锁，只是在更新数据的时候去判断之前有没有别的线程更新了这个数据。如果这个数据没有被更新，当前线程将自己修改的数据成功写入。如果数据已经被其他线程更新，则根据不同的实现方式执行不同的操作（例如报错或者自动重试）。乐观锁在Java中是通过使用无锁编程来实现，最常采用的是CAS算法，Java原子类中的递增操作就通过CAS自旋实现的。
        - 悲观锁适合写操作多的场景，先加锁可以保证写操作时数据正确。
        - 乐观锁适合读操作多的场景，不加锁的特点能够使其读操作的性能大幅提升。
        ```java
        // ------------------------- 悲观锁的调用方式 -------------------------
        // synchronized
        public synchronized void testMethod() {
            // 操作同步资源
        }
        // ReentrantLock
        private ReentrantLock lock = new ReentrantLock(); // 需要保证多个线程使用的是同一个锁
        public void modifyPublicResources() {
            lock.lock();
            // 操作同步资源
            lock.unlock();
        }
        // ------------------------- 乐观锁的调用方式 -------------------------
        private AtomicInteger atomicInteger = new AtomicInteger();  // 需要保证多个线程使用的是同一个AtomicInteger
        atomicInteger.incrementAndGet(); //执行自增1
        ```
    - 刚才提到了segment继承于ReetrantLock，那谈谈Synchronized和Lock的区别
   
    -  请你谈谈关于Synchronized和lock 
        - synchronized是Java的关键字，当它用来修饰一个方法或者一个代码块的时候，能够保证在同一时刻最多只有一个线程执行该段代码。JDK1.5以后引入了自旋锁、锁粗化、轻量级锁，偏向锁来有优化关键字的性能。
        - Lock是接口，synchronized是java关键字，内置实现
        - 在发生异常时，synchronized会自动释放线程占有的锁，因此不会导致死锁现象发生；而Lock在发生异常时，如果没有主动通过unLock()去释放锁，则很可能造成死锁现象，因此使用Lock时需要在finally块中释放锁
        - Lock可以让等待锁的线程响应中断，而synchronized却不行，使用synchronized时，等待的线程会一直等待下去，不能够响应中断；通过Lock可以知道有没有成功获取锁，而synchronized却无法办到。
    - 请你介绍一下Syncronized锁，如果用这个关键字修饰一个静态方法，锁住了什么？如果修饰成员方法，锁住了什么？
        - synchronized修饰静态方法以及同步代码块的synchronized (类.class)用法锁的是类，线程想要执行对应同步代码，需要获得类锁。synchronized修饰成员方法，线程获取的是当前调用该方法的对象实例的对象锁。
    - 死锁举例
        - 第一种synchronized方式死锁：线程thread1先获取锁locka，然后在同步块里嵌套竞争锁lockb。而线程thread2先获取锁lockb，然后在同步块里嵌套竞争锁locka
        - 第二种concurrent包Lock错误使用，导致死锁：java两种经典死锁例子，Lock发生死锁案列.
    - CAS
        - CAS（Compare-and-Swap），即比较并替换，是一种实现并发算法时常用到的技术，Java并发包中的很多类都使用了CAS技术。
        - CompareAndSwap的缩写，中文意思是：比较并替换。CAS 指令需要有 3 个操作数，分别是内存地址 V、旧的预期值 A 和新值 B。当执行操作时，只有当 V 的值等于 A，才将 V 的值更新为 B。整个比较并替换的操作对一个操作数来说是一个原子操作。
        - CAS的缺点 3点 https://www.cnblogs.com/loveLands/articles/9703474.html
    - 红黑树
        - 特点:每个节点非红即黑；根节点总是黑色的；每个叶子节点都是黑色的空节点（NIL节点）；如果节点是红色的，则它的子节点必须是黑色的（反之不一定）；从根节点到叶节点或空子节点的每条路径，必须包含相同数目的黑色节点（即相同的黑色高度）;
        - 红黑树这么优秀,为何不直接使用红黑树得了?
        - 说一下自己对于这个问题的看法：我们知道红黑树属于（自）平衡二叉树，但是为了保持“平衡”是需要付出代价的，红黑树在插入新数据后可能需要通过左旋，右旋、变色这些操作来保持平衡，这费事啊。你说说我们引入红黑树就是为了查找数据快，如果链表长度很短的话，根本不需要引入红黑树的，你引入之后还要付出代价维持它的平衡。但是链表过长就不一样了。至于为什么选 8 这个值呢？通过概率统计所得，这个值是综合查询成本和新增元素成本得出的最好的一个值。
    -  一致性hash
        - 一致性哈希，就是提供一个hashtable,它能在节点加入离开时不会导致映射关系的重大变化
        - 分布式一致性hash。如果Server的哈希等于Key的哈希，则把Key存放在该Server上；否则，寻找第一个大于Key哈希的Server，用于存放Key。但有Server增加、删除时，只要变动周边的Server映射关系即可，不用全部重新哈希。之所以有这样优良的特性是因为，Server和Key采用了同样的值域。还有最后一个问题，虚节点是如何产生的呢？也非常简单，就是在每个Server加个后缀，在做MD5哈希，取其32位。
        - MD5哈希; MD5的结果为一个160bit的数字，取其前32位作为一个Integer
    - arryalist和linkedlist的区别
        - 1.ArrayList是实现了基于动态数组的数据结构，而LinkedList是基于链表的数据结构；
        - 2.对于随机访问get和set，ArrayList要优于LinkedList，因为LinkedList要移动指针；
        - 3.对于添加和删除操作add和remove，一般大家都会说LinkedList要比ArrayList快，因为ArrayList要移动数据。但是实际情况并非这样，对于添加或删除，LinkedList和ArrayList并不能明确说明谁快谁慢，下面会详细分析。
    - 公平锁原理
        - 公平锁在锁释放后会严格按照等到队列去取后续值，而非公平锁在对于新晋线程有很大优势。
    - 联合索引
        - 两个或更多个列上的索引被称作联合索引，联合索引又叫复合索引。对于复合索引:Mysql从左到右的使用索引中的字段，一个查询可以只使用索引中的一部份，但只能是最左侧部分。
    - AQS 结合 公平锁
        - AQS底层机制.对java并发机制熟悉的人都知道底层基本上都是基于AQS实现的,即AbstractQueuedSynchronizer.而且AQS里面又维护了一个队列,可以实现线程排队机制,也可以做等待唤醒操作。那到底公平锁和非公平锁的区别在哪？仔细看一下,NonfairSync中的lock方法首先会通过CAS修改state,而FairSync则直接通过acquire获取。因为acquire最终还是通过CAS修改state,只是里面内置了排队机制.而非公平锁则直接修改state的值,无需排队
        - https://tech.meituan.com/2018/11/15/java-lock.html 根据代码可知，ReentrantLock里面有一个内部类Sync，Sync继承AQS（AbstractQueuedSynchronizer），添加锁和释放锁的大部分操作实际上都是在Sync中实现的。它有公平锁FairSync和非公平锁NonfairSync两个子类。ReentrantLock默认使用非公平锁，也可以通过构造器来显示的指定使用公平锁。通过上图中的源代码对比，我们可以明显的看出公平锁与非公平锁的lock()方法唯一的区别就在于公平锁在获取同步状态时多了一个限制条件：hasQueuedPredecessors()。
        - 首先ReentrantLock和NonReentrantLock都继承父类AQS，其父类AQS中维护了一个同步状态status来计数重入次数，status初始值为0。当线程尝试获取锁时，可重入锁先尝试获取并更新status值，如果status == 0表示没有其他线程在执行同步代码，则把status置为1，当前线程开始执行。如果status != 0，则判断当前线程是否是获取到这个锁的线程，如果是的话执行status+1，且当前线程可以再次获取锁。而非可重入锁是直接去获取并尝试更新当前status的值，如果status != 0的话会导致其获取锁失败，当前线程阻塞。
    - Object的方法都有哪些 https://zhb1208.iteye.com/blog/1418324
    - 怎么判断两个对象相等？
        - equals通常用来比较两个对象的内容是否相等，==用来比较两个对象的地址是否相等。Object类中的equals方法定义为判断两个对象的地址是否相等（可以理解成是否是同一个对象），地址相等则认为是对象相等。这也就意味着，我们新建的所有类如果没有复写equals方法，那么判断两个对象是否相等时就等同于“==”，也就是两个对象的地址是否相等。1、类未复写equals方法，则使用equals方法比较两个对象时，相当于==比较，即两个对象的地址是否相等。地址相等，返回true，地址不相等，返回false.2、类复写equals方法，比较两个对象时，则走复写之后的判断方式。通常，我们会将equals复写成：当两个对象内容相同时，则equals返回true，内容不同时，返回false。
    - equals和hashCode
        - hashCode的作用及与equals的关系。hashCode的作用是用来获取哈希码，也可以称作散列码。实际返回值为一个int型数据。用于确定对象在哈希表中的位置。Object中有hashcode方法，也就意味着所有的类都有hashCode方法。但是，hashcode只有在创建某个类的散列表的时候才有用，需要根据hashcode值确认对象在散列表中的位置，但在其他情况下没用。
    - 请你解释Object若不重写hashCode()的话，hashCode()如何计算出来的？
        - Object 的 hashcode 方法是本地方法，也就是用 c 语言或 c++ 实现的，该方法直接返回对象的 内存地址。
    - 请你解释为什么重写equals还要重写hashcode？
        - 因为自定义的类的hashcode()方法继承于Object类，其hashcode码为默认的内存地址，这样即便有相同含义的两个对象，比较也是不相等的
    - 你知道java8的新特性吗，请简单介绍一下
        - Lambda 表达式 − Lambda允许把函数作为一个方法的参数（函数作为参数传递进方法中。
        - Optional 类 − Optional 类已经成为 Java 8 类库的一部分，用来解决空指针异常。
- jvm
    - jvm中字符全部统一使用UNICODE编码
    - java中的异常全是throwable, 又分为error和exception。error是程序本身无法解决的，例如内存泄露，死循环等。exception是程序可以解决的，例如内存溢出，无效参数，下标越界，除数为零，数值溢出等。java中一般有两类异常，一个是throw语句，一类是runtimeexception

    - Java final volatile 关键字 volatile指令重排序 举个重排序例子
        - final
            - 对于一个final变量，如果是基本数据类型的变量，则其数值一旦在初始化之后便不能更改；如果是引用类型的变量，则在对其初始化之后便不能再让其指向另一个对象。
            - 在方法的参数中设一个final参数，则该参数如果被修改则会报错，这样防止不小心修改导致调用方法出错。
            - final方法：已知该方法功能完全满足需求，无需扩展。二是允许编译器将该方法转为inline的调用机制，直接将方法主体插入到调用处，不需要进行例行的压栈等操作。
        - volatile不能保证线程安全 https://blog.csdn.net/chenchaofuck1/article/details/51702388
        - volatile只能保证可见性 可见性指当一个线程修改了一个共享变量的值，其他线程能够立即得知这个修改，volatile的特殊规则就是read、load、use必须连续出现。assign、store、write动作必须连续出现。所以使用volatile变量能够保证必须先从主内存刷新最新的值，每次修改后必须立即同步回主内存当中。无法保证原子性，而自增操作并不是一个原子操作 https://kuaibao.qq.com/s/20180314G08I8P00?refer=spider
        - 禁止指令重排序优化。 
            - 1）当程序执行到volatile变量的读操作或者写操作时，在其前面的操作的更改肯定全部已经进行，且结果已经对后面的操作可见；在其后面的操作肯定还没有进行；
            - 2）在进行指令优化时，不能将在对volatile变量访问的语句放在其后面执行，也不能把volatile变量后面的语句放到其前面执行。
        - java 缓存一致性 https://blog.csdn.net/sdr_zd/article/details/81323519
        - Java并发编程中要保证的几个原则:原子性可见性有序性.
        - 缓存一致性协议。这类协议有MSI、MESI（Illinois Protocol）、MOSI、Synapse、Firefly及 Dragon Protocol等。
        
    - happens-before原则
        - 使用happens-before的概念来指定两个操作之间的执行顺序。由于这两个操作可以在一个线程之内，也可以是在不同线程之间。因此，JMM可以通过happens-before关系向程序员提供跨线程的内存可见性保证。 
    - JVM对Java做了什么 堆和栈 垃圾回收算法

    - jvm调优的方法
        - 栈进行动态扩展时如果无法申请到足够内存，会抛出 OutOfMemoryError 异常。可以通过 -Xss 这个虚拟机参数来指定每个线程的 Java 虚拟机栈内存大小，在 JDK 1.4 中默认为 256K，而在 JDK 1.5+ 默认为 1M：
        - 堆不需要连续内存，并且可以动态增加其内存，增加失败会抛出 OutOfMemoryError 异常。可以通过 -Xms 和 -Xmx 这两个虚拟机参数来指定一个程序的堆内存大小，第一个参数设置初始值，第二个参数设置最大值。
        - 和堆一样不需要连续的内存，并且可以动态扩展，动态扩展失败一样会抛出 OutOfMemoryError 异常。用于存放已被加载的类信息、常量、静态变量、即时编译器编译后的代码等数据。
        - 运行时常量池： Class 文件中的常量池（编译器生成的字面量和符号引用）会在类加载后被放入这个区域。
        - 调优参数 https://zhuanlan.zhihu.com/p/58896619
        - 调优过程 https://youzhixueyuan.com/jvm-performance-optimization.html
    - 直接内存 NIO nativeIO, 搞得像C++
        - 在 JDK 1.4 中新引入了 NIO 类，它可以使用 Native 函数库直接分配堆外内存，然后通过 Java 堆里的 DirectByteBuffer 对象作为这块内存的引用进行操作。这样能在一些场景中显著提高性能，因为避免了在堆内存和堆外内存来回拷贝数据。
        - 因为DirectByteBuffer是通过虚引用(Phantom Reference)来实现堆外内存的释放的。      
    - jvm的GC机制   
        - 引用计数
            - sys.getrefcount(1000) 就可以找到1000的引用计数。https://www.youtube.com/watch?v=RHcOlcEh5lA
            - 引用计数加1的共有四种情况：创建对象 引用计数为1，其他变量指向它+1, 传参+1，加入容器+1
        - 可达性分析
            - 没有被GCroot引用的对象都是可以被回收的对象。
            - 哪些是GCroot的对象? 栈中引用的对象，方法区的静态类属性中引用的对象，方法区中的常量引用对象，JNI本地方法引用的对象。
        - JVM两种垃圾回收算法
            - 标记-清除；标记-整理；
        - 常见的垃圾回收器
            - serial garbage collector: 单线程GC
            - Parallel garbage collector: 多线程GC
            - CMS GC
            - G1：类似标记-整理，jdk7引进的GC，jdk9默认的GC, 多线程，高并发，分代收集(不再严格区分新生代老年代，直接是一块一块的内存区域)，低暂停(因为有可预测的停顿，存一张表)，逐步取代CMS GC。就回答这个GC就可以。
                - 步骤：初始标记，并发标记，最终标记，筛选回收。
        - cms停顿了几次？为什么要有这些停顿？ https://zhuanlan.zhihu.com/p/42934904
            - CMS并非没有暂停，而是用两次短暂停来替代串行标记整理算法的长暂停，它的收集周期是这样：初始标记(CMS-initial-mark) -> 并发标记(CMS-concurrent-mark) -> 重新标记(CMS-remark) -> 并发清除(CMS-concurrent-sweep) ->并发重设状态等待下次CMS的触发(CMS-concurrent-reset)。其中的1，3两个步骤需要暂停所有的应用程序线程的。第一次暂停从root对象开始标记存活的对象，这个阶段称为初始标记；第二次暂停是在并发标记之后， 暂停所有应用程序线程，重新标记并发标记阶段遗漏的对象（在并发标记阶段结束后对象状态的更新导致）。第一次暂停会比较短，第二次暂停通常会比较长，并且 remark这个阶段可以并行标记。
        - FullGC,MinorGC https://youzhixueyuan.com/the-difference-between-minor-gc-major-gc-full-gc.html
        - Minor GC和Major GC其实就是年轻代GC和年老年GC的俗称。而在Hotspot VM具体实现的收集器：Serial GC, Parallel GC, CMS, G1 GC中，大致可以对应到某个Young GC和Old GC算法组合。
        - Survivor的存在意义，就是减少被送到老年代的对象，进而减少Full GC的发生，Survivor的预筛选保证，只有经历16次Minor GC还能在新生代中存活的对象，才会被送到老年代。永远有一个survivor space是空的，另一个非空的survivor space无碎片。
        - Full GC定义是相对明确的，就是针对整个新生代、老生代、元空间（metaspace，java8以上版本取代perm gen）的全局范围的GC。
        - 深入详解JVM内存模型与JVM参数详细配置  https://youzhixueyuan.com/jvm-memory-model-and-parameter-configuration.html
        - 垃圾回收算法： https://youzhixueyuan.com/jvm-garbage-collection-algorithm.html
    - java类加载器有哪些
        -  方法 loadClass()抛出的是 java.lang.ClassNotFoundException异常；方法 defineClass()抛出的是 java.lang.NoClassDefFoundError异常。
        - 启动（Bootstrap）类加载器  扩展（Extension）类加载器  系统（System）类加载器
        - 代理模式:双亲委派模型的工作过程如下：如果一个类加载器收到了类加载的请求，它首先不会自己去尝试加载这个类，而是把这个请求委派给父类加载器去完成，每一个层次的类加载器都是如此，因此所有的加载请求最终都会传送到顶层的启动类加载器中，只有当父类加载器反馈自己无法完成这个加载请求（它的搜索范围内没找到这个类）时，自加载器才会尝试自己加载。
        - 代理模式:双亲委派模型是为了保证 Java 核心库的类型安全。所有 Java 应用都至少需要引用 java.lang.Object类，也就是说在运行的时候，java.lang.Object这个类需要被加载到 Java 虚拟机中。如果这个加载过程由 Java 应用自己的类加载器来完成的话，很可能就存在多个版本的 java.lang.Object类，而且这些类之间是不兼容的。通过双亲委派模型，对于 Java 核心库的类的加载工作由启动类加载器来统一完成，保证了 Java 应用所使用的都是同一个版本的 Java 核心库的类，是互相兼容的。
        - Class.forName是一个静态方法，同样可以用来加载类。该方法有两种形式：Class.forName(String name, boolean initialize, ClassLoader loader)和 Class.forName(String className)。第一种形式的参数 name表示的是类的全名；initialize表示是否初始化类；loader表示加载时使用的类加载器。第二种形式则相当于设置了参数 initialize的值为 true，loader的值为当前类的类加载器。
    - java反射机制及应用
        - 反射则是一开始并不知道我要的类对象是什么，自然也无法使用 new 关键字来创建对象了。反射就是在运行时才知道要初始化/操作的类是什么，并且可以在运行时获取类的完整构造，并调用对应的方法。
        - 获取反射中的Class对象
            - 第一种，使用 Class.forName 静态方法。当你知道该类的全路径名时，你可以使用该方法获取 Class 类对象。 Class.forName("类的路径").
            - 第二种，使用 .class 方法。类名.class；
            - 第三种，使用类对象的 getClass() 方法。实例.getClass()。
        - 通过反射创建类对象   Class 对象的 newInstance() 方法   Constructor 对象的 newInstance() 方法
        - 反射的功能：通过反射获取类属性、成员变量和方法、构造器，在运行时创建对象，在运行时调用对象的方法
            - getFields() 方法 ;  getDeclaredFields() 
    - synchronized 底层实现，4种锁。https://blog.csdn.net/javazejian/article/details/72828483
        - synchronized可以保证在同一个时刻，只有一个线程可以执行某个方法或者某个代码块(主要是对方法或者代码块中存在共享数据的操作)，同时synchronized可保证一个线程的变化(主要是共享数据的变化)被其他线程所看到（保证可见性，完全可以替代Volatile功能），这点确实也是很重要的。
        - synchronized底层语义原理：Java 虚拟机中的同步(Synchronization)代码块基于进入和退出管程(Monitor)对象实现， 同步方法并不是调用指令读取运行时常量池中方法的 ACC_SYNCHRONIZED 标志来隐式实现的。
        - 存在哪？ java对象头 https://www.jianshu.com/p/a1e8170ed63c
        - Java中提供了两种实现同步的基础语义：synchronized方法和synchronized块
        - synchronized锁的状态；共有四种，只能从低到高升级，不会出现锁的降级。
            - 无锁
                - 无锁的特点就是修改操作在循环内进行，线程会不断的尝试修改共享资源。如果没有冲突就修改成功并退出，否则就会继续循环尝试。如果有多个线程修改同一个值，必定会有一个线程能修改成功，而其他修改失败的线程会不断重试直到修改成功。上面我们介绍的CAS原理及应用即是无锁的实现。无锁无法全面代替有锁，但无锁在某些场合下的性能是非常高的。
            - 偏向锁
                - 为了减少同一线程获取锁(会涉及到一些CAS操作,耗时)的代价而引入偏向锁。如果一个线程获得了锁，那么锁就进入偏向模式，此时Mark Word 的结构也变为偏向锁结构，当这个线程再次请求锁时，无需再做任何同步操作，即获取锁的过程。但是对于锁竞争比较激烈的场合，偏向锁就失效了。
            - 轻量级锁(1.6之后加入的)
                - 倘若偏向锁失败，虚拟机并不会立即升级为重量级锁，此时Mark Word 的结构也变为轻量级锁的结构。轻量级锁能够提升程序性能的依据是“对绝大部分的锁，在整个同步周期内都不存在竞争”，注意这是经验数据。需要了解的是，轻量级锁所适应的场景是线程交替执行同步块的场合，如果存在同一时间访问同一锁的场合，就会导致轻量级锁膨胀为重量级锁。
            - 自旋锁
                - 虚拟机让当前想要获取锁的线程做几个空循环(这也是称为自旋的原因)，一般不会太久，可能是50个循环或100循环，在经过若干次循环后，如果得到锁，就顺利进入临界区。如果还不能获得锁，那就会将线程在操作系统层面挂起，这就是自旋锁的优化方式，这种方式确实也是可以提升效率的。最后没办法也就只能升级为重量级锁了。
            - 重量级锁  
                - 效率低下，因为监视器锁（monitor）是依赖于底层的操作系统的Mutex Lock来实现的，而操作系统实现线程之间的切换时需要从用户态转换到核心态，这个状态之间的转换需要相对比较长的时间。
                - https://juejin.im/post/5bfe6ddee51d45491b0163eb#heading-3
        - synchronized的可重入性
            - 当一个线程再次请求自己持有对象锁的临界资源时，这种情况属于重入锁，请求将会成功，在java中synchronized是基于原子性的内部锁机制，是可重入的，因此在一个线程调用synchronized方法的同时在其方法体内部调用该对象另一个synchronized方法，是允许的。
    - 实现接口与继承类的区别
        - 一个类只能继承一个类，但是可以实现多个接口。接口里面的方法都是抽象方法，必须要重写所有的方法。接口抽象的方法都要被重写，而继承的类不必这样。继承一般开发中用的会相比少一点,接口相比就应该会多一点.，接口主要是实现一种松耦合，便于以后的维护、升级，继承主要是提高代码的可重用性，很多东西都可以在父类中做好。子类可以直接用.
   
    - JavaNIO和IO区别，如果分别用他们实现QQ有什么区别
        - NIO是为了弥补IO操作的不足而诞生的，NIO的一些新特性有：非阻塞I/O，选择器，缓冲以及管道。管道（Channel），缓冲（Buffer） ，选择器（ Selector）是其主要特征。1,IO是面向流的，NIO是面向块（缓冲区）的。2，IO是阻塞的，NIO是非阻塞的。
    - 线程池知道吗？为什么用线程池，有什么好处 https://blog.csdn.net/qq_33453910/article/details/81413285
        - 不使用线程池的话，所创建的线程数无法控制，比如一下子创建了几百几千个线程，电脑一下子就崩溃了。1:提高效率 创建好一定数量的线程放在池中，等需要使用的时候就从池中拿一个，这要比需要的时候创建一个线程对象要快的多。2:方便管理 可以编写线程池管理代码对池中的线程统一进行管理，比如说系统启动时由该程序创建100个线程，每当有请求的时候，就分配一个线程去工作， 如果刚好并发有101个请求，那多出的这一个请求可以排队等候，避免因无休止的创建线程导致系统崩溃
        - java中的有哪些线程池？1.newCachedThreadPool创建一个可缓存线程池程；2.newFixedThreadPool 创建一个定长线程池；3.newScheduledThreadPool 创建一个定长线程池；4.newSingleThreadExecutor 创建一个单线程化的线程池
    - 栈上的空间什么时候分配的 
        - Java栈内存是每个线程执行的时候分配的。 https://blog.csdn.net/Renirvana/article/details/54630785

- 微服务相关
    - 微服务vs巨石服务 https://www.cnblogs.com/linezero/p/microservices.html
        - 最后还要强调：系统分解的目标并不仅仅是搞出一堆很小的服务，这不是目标；真正的目标是解决巨石型应用在业务急剧增长时遇到的问题。
        - High frequency release.High density worker role.Flexible Scale up.Quickly start.Friendly to streaming.
        - 每个服务足够内聚，足够小，代码容易理解、开发效率提高；服务之间可以独立部署，微服务架构让持续部署成为可能；每个服务可以各自进行x扩展和z扩展，而且，每个服务可以根据自己的需要部署到合适的硬件服务器上；提高容错性（fault isolation），一个服务的内存泄露并不会让整个系统瘫痪；系统不会被长期限制在某个技术栈上。
        - 开发人员要处理分布式系统的复杂性；开发人员要设计服务之间的通信机制，对于需要多个后端服务的user case，要在没有分布式事务的情况下实现代码非常困难；
    - 1.微服务架构的通信机制
        - 方案 RESTful HTTP请求 + 内部服务之间通信。需要API gateway，由它负责与客户度对接，并将客户端的请求转化成对内部服务的一系列调用。这样做还有个好处是，服务升级不会影响到客户端，只需要修改API gateway即可。
            - API gateway：内部服务之间的通信方式有两种：基于HTTP协议的同步机制（REST、RPC）；基于消息队列的异步消息处理机制（AMQP-based message broker）。
            - Dubbo是阿里巴巴开源的分布式服务框架，属于同步调用，当一个系统的服务太多时，需要一个注册中心来处理服务发现问题，例如使用ZooKeeper这类配置服务器进行服务的地址管理：服务的发布者要向ZooKeeper发送请求，将自己的服务地址和函数名称等信息记录在案；服务的调用者要知道服务的相关信息，具体的机器地址在ZooKeeper查询得到。这种同步的调用机制足够直观简单，只是没有“订阅——推送”机制。
            - AMQP-based的代表系统是kafka、RabbitMQ等。这类分布式消息处理系统将订阅者和消费者解耦合，消息的生产者不需要消费者一直在线；消息的生产者只需要把消息发送给消息代理，因此也不需要服务发现机制。
            - 两种通信机制都有各自的优点和缺点，实际中的系统经常包含两种通信机制。例如，在分布式数据管理中，就需要同时用到同步HTTP机制和异步消息处理机制。
    - 2.分布式数据管理
        - （1）A读B请求 单缺点是多一次RPC调用、而且调用的服务B必须保持在线。处理：A处存放一份信用卡额度的副本
        - （2）处理更新请求 当一份数据位于多个服务上时，必须保证数据的一致性。分布式事务（Distributed transactions）
    - 六种微服务架构的设计模式
        - 聚合器微服务设计模式/代理微服务设计模式客户端并不聚合数据，但会根据业务需求的差别调用不同的微服务。代理可以仅仅委派请求，也可以进行数据转换工作。
        - 链式微服务设计模式/分支微服务设计模式
        - 数据共享微服务设计模式.自治是微服务的设计原则之一，就是说微服务是全栈式服务。但在重构现有的“单体应用（monolithic application）”时，SQL数据库反规范化可能会导致数据重复和不一致。因此，在单体应用到微服务架构的过渡阶段，可以使用这种设计模式，如下图所示：
        - 异步消息传递微服务设计模式.虽然REST设计模式非常流行，但它是同步的，会造成阻塞。因此部分基于微服务的架构可能会选择使用消息队列代替REST请求/响应.
    - 微服务架构的5个关键问题：https://www.infoq.cn/article/btx6geZA_qwmyr07LbOb
        - OAuth2 的四种模式该如何选择？
        - 如何理解 Apollo 配置中心的架构？
        - 微服务网关 Zuul 承担哪些核心职责
    - 设计微服务的最佳实践是什么 https://cloud.tencent.com/developer/article/1346868
    - RPC 的实现原理  https://liuzhengyang.github.io/2016/12/16/rpc-principle/
        - 首先需要有处理网络连接通讯的模块，负责连接建立、管理和消息的传输。其次需要有编解码的模块，因为网络通讯都是传输的字节码，需要将我们使用的对象序列化和反序列化。剩下的就是客户端和服务器端的部分，服务器端暴露要开放的服务接口，客户调用服务接口的一个代理实现，这个代理实现负责收集数据、编码并传输给服务器然后等待结果返回。
    - 说说 Dubbo 的实现原理 https://www.zhihu.com/question/52133065/answer/129153953
        - dubbo作为rpc框架，实现的效果就是调用远程的方法就像在本地调用一样。如何做到呢？就是本地有对远程方法的描述，包括方法名、参数、返回值，在dubbo中是远程和本地使用同样的接口；然后呢，要有对网络通信的封装，要对调用方来说通信细节是完全不可见的，网络通信要做的就是将调用方法的属性通过一定的协议（简单来说就是消息格式）传递到服务端；服务端按照协议解析出调用的信息；执行相应的方法；在将方法的返回值通过协议传递给客户端；客户端再解析；在调用方式上又可以分为同步调用和异步调用；简单来说基本就这个过程
    - rest 幂等性 http://blog.720ui.com/2016/restful_idempotent/
    - 如何解决api层的速率限制或支持重试和断路等功能 == 为什么要用 service mesh ？
        - 网络挑战是由于Kubernetes等流行的容器编排软件所带来的。Kubernetes构建的就是要支持微服务架构。这允许开发和运维人员将功能抽象成一组pod，并将其作为“service”暴露出来，并通过定义好的API进行访问。Kubernetes支持DNS和基于TCP的L4负载均衡。基于TCP L4负载均衡的问题是它无法与L7（应用程序和API层）交互。对于任何L4负载均衡都是如此；它不是容器和Kubernetes独有的东西。L4负载均衡提供了对连接级别（TCP）协议和指标的可见性，但仅此而已。这使得很难（真的不可能）解决高阶问题，例如每秒请求数或事务等L7指标以及基于路径分割流量（路由请求）。这也意味着您无法在API层进行速率限制或支持重试和断路等关键功能。在service mesh中，所有流量都通过sidecar代理进行有效路由。因此它可以自动生成并将所需的指标提供给网格的其它部分。对于在容器环境中部署传统应用程序的组织而言，这非常有价值。
    - 如何保持用户状态？ https://zhaohuabing.com/2018/05/22/user_authentication_authorization/
        - Token和Seesion主要的不同点是存储的地方不同。Session是集中存储在服务器中的；而Token是用户自己持有的，一般以cookie的形式存储在浏览器中。Token中保存了用户的身份信息，每次请求都会发送给服务器，服务器因此可以判断访问者的身份，并判断其对请求的资源有没有访问权限。没有了cookie，session就没用了。
    - 实现单点登录
        - 
    - Now	Technical transfer；	Replicate service for more partners；	Open API for Speech/text Models
    - 必要的微服务架构知识
        - API网关 http://developer.51cto.com/art/201807/579943.htm
        - 部署方式 蓝绿发布，Rolling update（滚动发布） 灰度发布/金丝雀部署 https://www.jianshu.com/p/022685baba7d
    
- 开源框架/分布式
    - 什么是分布式事务 怎么做 https://www.cnblogs.com/savorboard/p/distributed-system-transaction-consistency.html
        - CAP定理 一致性(Consistency) ： 客户端知道一系列的操作都会同时发生(生效)；可用性(Availability) ： 每个操作都必须以可预期的响应结束。分区容错性(Partition tolerance) ： 即使出现单个组件无法可用,操作依然可以完成。具体地讲在分布式系统中，在任何数据库设计中，一个Web应用至多只能同时支持上面的两个属性。显然，任何横向扩展策略都要依赖于数据分区。因此，设计人员必须在一致性与可用性之间做出选择。
        - 其中，XA 是一个两阶段提交协议，该协议分为以下两个阶段：
        - 第一阶段：事务协调器要求每个涉及到事务的数据库预提交(precommit)此操作，并反映是否可以提交.
        - 第二阶段：事务协调器要求每个数据��提交数据。
        - BASE理论；Basically Available（基本可用）；Soft state（软状态）；Eventually consistent（最终一致性）
    - 分布式锁
        - 2.1为何需要分布式锁。效率 https://juejin.im/post/5bbb0d8df265da0abd3533a5
        - 5.1Redis分布式锁简单实现
    - spring ioc aop springboot差别
    - redis 几种数据结构，内部都是byte[]数组哇
        - https://zhuanlan.zhihu.com/p/78896005
    - redis主从复制 Remote Dictionary Server
        - azure redis
        - 缓存穿透，缓存与数据库双写一致 https://www.cnblogs.com/Java3y/p/10266306.html
        - 史上最全Redis面试49题(含答案):哨兵+复制+事务+集群+持久化等: https://segmentfault.com/a/1190000017339258
        - Redis有哪几种数据淘汰策略？
        - 主从复制是为了数据备份
        - Redis是一个基于内存的高性能Key-Value存储系统，它支持存储的value类型很多，包括下面的和有序集合）。这些数据类型都支持push/pop、add/remove以及取交集和并集等丰富的操
        - 数据结构 -- hash：通过 key(用户ID) + field(属性标签) 就可以操作对应属性数据了，既不需要重复存储数据，也不会带来序列化和并发修改控制的问题。很好的解决了问题。 list：Redis list的实现为一个双向链表，Redis内部的很多实现，包括发送缓冲队列等也都是用的这个数据结构。set 的内部实现是一个 value永远为null的HashMap，实际就是通过计算hash的方式来快速排重的，这也是set能提供判断一个成员是否在集合内的原因。Redis sorted set的内部使用HashMap和跳跃表(SkipList)来保证数据的存储和有序，HashMap里放的是成员到score的映射，而跳跃表里存放的是所有的成员，排序依据是HashMap里存的score,使用跳跃表的结构可以获得比较高的查找效率，并且在实现上比较简单。
    - thrift RPC原理
    
    - 如果登陆了如何其他服务器知道
    - 微服务架构的身份认证问题
        - SSO原理，应用场景
            - 这种方案意味着每个面向用户的服务都必须与认证服务交互，这会产生大量非常琐碎的网络流量和重复的工作，当动辄数十个微应用时，这种方案的弊端会更加明显。单点登录SSO（Single Sign On）说得简单点就是在一个多系统共存的环境下，用户在一处登录后，就不用在其他系统中登录，也就是用户的一次登录能得到其他所有系统的信任。
        - 分布式session方式
            - 例如阿里有很多系统分割为多个子系统，独立部署后，不可避免的会遇到会话管理的问题，类似这样的电商网站一般采用分布式Session实现。再进一步可以根据分布式Session，建立完善的单点登录或账户管理系统。
        -  客户端 Token 与 API 网关结合
    - springboot 和 springmvc 和 spring 区别
    - 缓存一致性

    - LVS负载均衡怎么支持高并发，负载均衡发生在网络的哪一层
        - LVS是四层负载均衡，也就是说建立在OSI模型的第四层——传输层之上，传输层上有我们熟悉的TCP/UDP，LVS支持TCP/UDP的负载均衡。
    - 实现分布式锁
    - 聊聊ZK和Consul
    - ZK的实现，他是用来干嘛的
  
- 数据库相关
    -  InnoDB索引和MyISAM索引的区别：http://www.voidcn.com/article/p-khushvii-qh.html
        一是主索引的区别，InnoDB的数据文件本身就是索引文件。而MyISAM的索引和数据是分开的。
        二是辅助索引的区别：InnoDB的辅助索引data域存储相应记录主键的值而不是地址。而MyISAM的辅助索引和主索引没有多大区别
    - 数据库索引B树和B+树有什么区别，B+树的高度何时发生改变
        - 卫星数据：指的是索引元素所指向的数据记录。比如数据库中的某一行。B树中无论中间节点还是叶子节点都带有卫星数据。B+树中，只有叶子节点带卫星数据，其他中间节点仅仅是索引，没有数据关联。
        - 综合起来，B+树比B-树优势有三个：1、IO次数更少2、查询性能稳定3、范围查询简便。
    - 创建索引的过程
    - Like查询的过程
    - 百度真题
        - 面项目数据库，全程怼数据库（数据库索引优化，联合索引，如何建立索引，数据分裤分表，种类使用场景，如何对数据进行分裤有哪些方式）。面项目数据库（写出数据的表结构表中的字段，表之间的关联，用ER图画，不会，忘了。他说没关系，现在让你设计这个数据库表结构你会如何设计，设计完后，他说需求我写sql语句。我写的比较low，他们会不会数据库连接，左连接，右连接，全链接等）
    - 数据库 事务 隔离级别
        - 在说分布式事务之前，我们先从数据库事务说起。 数据库事务可能大家都很熟悉，在开发过程中也会经常使用到。但是即使如此，可能对于一些细节问题，很多人仍然不清楚。比如很多人都知道数据库事务的几个特性：原子性(Atomicity )、一致性( Consistency )、隔离性或独立性( Isolation)和持久性(Durabilily)，简称就是ACID。但是再往下比如问到隔离性指的是什么的时候可能就不知道了，或者是知道隔离性是什么但是再问到数据库实现隔离的都有哪些级别，或者是每个级别他们有什么区别的时候可能就不知道了
    - 数据库索引数据结构  哈希，B+树索引，优劣及应用比较，时间复杂度分析

- 操作系统 线程和进程 为什么切换线程消耗小 什么时候进程什么时候线程 虚拟内存 页式存储
    - google的： 进程切换比线程切换开销大是因为进程切换时要切页表，而且往往伴随着页调度，因为进程的数据段代码段要换出去，以便把将要执行的进程的内容换进来。本来进程的内容就是线程的超集。而且线程只需要保存线程的上下文（相关寄存器状态和栈的信息）就好了，动作很小\
    - 内存置换算法 FIFO LRU LFU OPT clock
    - IO多路复用，五大IO模型
        -  select poll,epoll都是IO多路复用的一种机制，就是通过一种机制可以监视多个文件描述符，一旦某个文件描述符就绪（一般是读就绪或者写就绪），就能够通知进程进行相应的读写操作，他们三个本质上都是同步IO，因为 它们都需要在读写事件就绪后自己负责读写操作，也就是读写过程中是阻塞的，而异步IO无需自己进行读写，它只负责发起事件具体的实现由别的完成
        - poll: 1、大量的fd的数组被整体复制于用户态和内核地址空间之间，而不管这样的复制是不是有意义。 2、poll还有一个特点是“水平触发”，如果报告了fd后，没有被处理，那么下次poll时会再次报告该fd
        -  epoll: epoll支持水平触发和边缘触发，最大的特点在于边缘触发，它只告诉进程哪些fd刚刚变为就需态，并且只会通知一次。还有一个特点是，epoll使用“事件”的就绪通知方式，通过epoll_ctl注册fd，一旦该fd就绪，内核就会采用类似callback的回调机制来激活该fd，epoll_wait便可以收到通知

- 多线程
    - 概念性问答题

- 开放性问题
    - 了解设计模式吗？
    - 场景题 额度调整不加锁?
    - 缓存系统如何提高命中率? https://www.cnblogs.com/dinglang/p/6117309.html
        - 通过缓存预加载（预热）、增加存储容量、调整缓存粒度、缓存的失效和更新策略等手段来提高命中率
    - 如何设计token？
        token 加密+ hash
    - 如何将长链接转为短链接
        - https://www.cnblogs.com/bluestorm/p/9424858.html

- 反问
    - 公司技术栈

### 技术面问题
- [史上最全阿里面试题](https://zhuanlan.zhihu.com/p/46144296)
- [知名公司的java面试题](https://www.techug.com/post/java-volatile-keyword.html)
- JMM主要就是围绕着如何在并发过程中如何处理原子性、可见性和有序性这3个特征来建立的，通过解决这三个问题，可以解除缓存不一致的问题。而volatile跟可见性和有序性都有关。
- [经典的133个问题列表]()
- [乐观锁](https://www.cnblogs.com/Mainz/p/3546347.html)
    - [两种锁的使用场景 和 ](https://juejin.im/post/5b4977ae5188251b146b2fc8)
    从上面对两种锁的介绍，我们知道两种锁各有优缺点，不可认为一种好于另一种，像乐观锁适用于写比较少的情况下（多读场景），即冲突真的很少发生的时候，这样可以省去了锁的开销，加大了系统的整个吞吐量。但如果是多写的情况，一般会经常产生冲突，这就会导致上层应用会不断的进行retry，这样反倒是降低了性能，所以一般多写的场景下用悲观锁就比较合适。
- [java面试宝典](https://funtl.com/zh/interview/Java-%E9%9D%A2%E8%AF%95%E5%AE%9D%E5%85%B8-%E8%AF%B4%E8%AF%B4-SQL-%E4%BC%98%E5%8C%96%E4%B9%8B%E9%81%93.html)
- 这个人写的程序和人生经验，挺好 https://coolshell.cn/
- 外企 面经 https://www.diycode.cc/topics/220
