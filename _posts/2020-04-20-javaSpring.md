---
layout: post
title: javaSpring
tags: java
categories: java
---
javaEE基础（共49小时的视频，4月20日开始）【上次45小时的6天学完，一天可以学习7.5小时的视频】
1. 45 16h56m 尚硅谷Struts2视频教程：BV1MW411u7uG
- since 2020-04-20，共45小节，17小时。预期2天学完。学完记得给自己出一张卷子。（4月20日 P1-P5，4月23日周四=P6-P45，马马虎虎的看的，没有看完，感觉就是佟刚教你一步一步教你用一个MVC的框架，没啥意思 ）
    - 貌似目前都用的是springmvc
    - struct2使用filter作为控制器
    - filter和servlet的不同
        - Filter有一个filterchain，这个api在servlet中没有
    - struct2是一个用来开发MVC应用程序的框架
        - 提供了输入合法性验证
        - 统一的布局
        - 可扩展性好
    - action 如何访问 web 资源
        - 常规如何访问web资源
            - 和servlet api解耦方式：访问有限servlet api对象。只能获取map
                - actionContext
                - aware接口
                - 可以得到各种map。例如applicationMap,sessionmap,requestMap,parameterMap
            - servlet api耦合方法 
                - servletActionContext，可以获取整个api对象
    - struts-default.xml 
        - 允许动态调用的定义
        - 关于struts2请求扩展名问题，struts.action.extension定义扩展名
        - 在strcts.xml里面配置struts可以受理的请求的扩展名 .action, .do等奇奇怪怪的请求
    - 对一个表中不同的列进行排序：在数据库中就排好
    - struts2主题，可以用在xml或者jsp中配置
    - 使用paramsprepareparamsstack拦截器栈后的运行流程
        - 和默认的拦截器栈defaultstack一样都是拦截器栈，定义的一组有顺序的拦截器，struts-default默认使用的是defaultstack
    - struts2的运行原理
    

2. 25 10h44m 尚硅谷Hibernate4视频教程：BV1KW411u7GJ
- since 2020-04-24周五，共25小节，10.44小时。预期1天学完。学完记得给自己出一张卷子。佟刚, 4月24日学习P1-P20,讲得实在太无聊了,没听完)
    - 一个java的持久化ORM框架：把对象保存到数据库中，crud+加载(根据特定的OID，把对象加载到内存)。ORM对象/关系映射，类(表)，对象(表的行)，属性(表的列)。ORM程序员把对数据库的操作转化为对对象的操作。元素据-描述数据的数据。元数据采用xml格式
    - ORM框架是对jdbc的封装（代码更短）。流行的框架：H，myBatis, toplink,ojb
    - 创建hibernate.cfg.xml配置文件，创建持久化类，创建对象关系映射文件，通过h api编写访问数据库的api。
    - session缓存
        - 一级缓存。读入session之后会缓存起来，下一次发送查询请求先会查询缓存，flush使数据库和缓存中的一致。reflesh把数据库的同步到内存，
    - session的核心方法
        - get和load方法的区别
            - get会立即加载对象，load若不使用这个对象，则不会立即执行查询操作，而返回一个代理对象。
            - load可能抛出lazyInitializationException异常
            - 若数据表中没有对应的记录，session也没有被关闭，get返回null,而load如不使用该对象的属性，则没关系，否则抛出异常
        - update，无论游离对象和数据表的记录是否一致，都会发送update语句。
        - saveorupdate，临时对象save，游离对象update
        - dalete，删除游离对象和持久化对象，只要oid和数据表中的记录存在对应，则删除，如果不存在对应的数据，则抛出异常
        - evict,从缓存中把指定的持久化对象移除
        - dowork, 调用存储过程
    - hibernate的配置文件
        - 可以有两种格式, heibernate.properties或者上述xml那样.推荐xml格式.
    - hibernate-mapping文件
        - package指定包名:
            - id,主键生成策略
        - 映射:一对多映射关系
            - 一对多关联关系, '<'many-to-one'>'
            - 双向1对多,
    

3. 36 09h31m 尚硅谷Spring4视频教程：BV1KW411u7An
- since 2020-04-25周六，共36小节，9.3小时。预期1天学完。学完记得给自己出一张卷子。佟刚,4月24日-4月24日，简单看了一遍，了解知识，重点在后面自己跟着敲项目吧！    
    - spring是一个开源框,简化企业级开发而生,EJB,spring的IOC和AOP的控制框架
        - spring是轻量级的,不需要实现接口,不需要继承父类,润物静无声
        - 依赖注入
        - 最底层是核心容器,beans, core, context,SPeL
        - aop, aspects, instrumentation, messeging
        - data access, web
    - 安装spring插件
    - springbean配置文件，配置bean（id,class--由spring反射创建这么一个对象,name），完成创建对象和对属性赋值的功能。
    - spring中bean的配置。
        - IOC反转控制，容器主动把资源推送给组件，反转资源获取的方向。
    - IOC的前生：
        - 分离接口与实现
        - 抽象工厂模式
    - 通过注解配置BEAN
    - AOP基础
    - 前置通知，后置通知，返回通知，异常通知，环绕通知
    - 切面的优先级
    - 使用jdbc
    - 事务管理

4. 13 02h47m 尚硅谷SSH整合综合案例：BV12s411E7Cp
- since 2020-04-26周日，共13小节，2.47小时。预期半天学完。学完记得给自己出一张卷子。

5. 60 08h33m 尚硅谷SpringMVC视频教程：BV1mW411M7YA
- since 2020-04-26周日，共60小节，8.3小时。预期半天学完。学完记得给自己出一张卷子。

6. spring 的 IDEA版本  BV1Sb411s7vP

- since 2020-07-25 周六，共12小时，预期8小时弄完
- 第一天：spring 框架的概述以及spring中基于xml的IOC配置
  - spring是什么
    - 全栈级轻量级的 spring framework 
    - ![image-20200725222616398](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20200725222616398.png)
  - spring的两大核心 IOC和AOP 
    - ![image-20200725223335787](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\image-20200725223335787.png)
    - 容器存放的是什么？为什么叫容器？
      - 容器就是map
        - ClassPathXmlApplicationContext: 它可以加载类路径下的配置文件，要求配置文件必须在类路径下，不在的话，加载不了
        - FileSystemXmlApplicationContext: 它可以加载磁盘任意路径下的配置文件
        - AnnotationConfigApplicationContext: 它是用于读取注解创建容器的
      - 核心容器两个接口
        - ApplicationContext是立即加载的，一度配置文件马上创建，读配置文件的时候创建对象，（单例对象适用），开发中采用此接口，可以在配置文件中表示是单例立即创建还是多例延迟创建
        - BeanFactory在构建核心容器的时候，是延迟加载的方式，（多例对象适用）
    - bean在计算机英语中，有可重用组件的含义
      - Spring Bean是被实例的，组装的及被Spring 容器管理的Java对象。
      - 把对象创建交给spring来管理
        - 创建Bean的三种方式
          - 使用默认构造函数创建
          - 使用普通工厂中的方法创建对象
          - 使用工厂中的静态方法创建对象
        - Bean对象的作用范围
          - bean标签的scope属性，用于指定bean的作用范围，单例，prototype多例、request作用于web应用的请求范围，session作用域web应用的会话范围，global-session不是集群环境就是session
        - bean对象的生命周期
          - 单例对象
            - 当容器创建时，对象出生，只要容器在，对象一直活着，容器销毁，对象消亡
          - 多例对象
            - 当使用对象时spring框架创建，对象在使用过程中一直活着，当对象长时间不用，且没有别的对象引用时，由java的垃圾回收器回收
  - spring的发展历程和优势
  - spring的体系结构
  - 曾经案例中的问题
  - 工厂模式解耦
  - spring中基于XML的IOC环境搭建
  - 依赖注入
    - IOC（Inversion of Control）的作用，降低程序间的耦合，依赖关系交给spring管理
    - 在当前类中需要用到其他类的对象，由spring为我们提供，我们只需要在配置文件中说明
    - 对依赖关系的维护成为依赖注入
    - 能注入的类型：
      - 基本类型和String
      - 其他bean类型
      - 复杂类型/集合类型
    - 注入方式：构造函数/set/注解
      - 构造函数：【type，Index=0/1, name指定名称参数赋值（常用），三个一样】，value，【缺点，每种参数的组合都需要一个构造函数】 constructor-arg
      - set方法注入：property【创建对象没有明显的限制，可以直接使用默认的构造函数】，如果某个成员必须右值，则可能没有执行Set方法
      - 
  - 学完这个内容能用在什么地方
- 第二天：spring中基于注解的IOC和IOC案例
  - 注解和xml配置实现的功能是一样的，都是为了解耦合
  - 注解类型
    - 创建对象的注解：和xml配置文件中编写一个bean标签的功能一样
    - 用于注入数据的：和xml配置文件中的Bean标签写一个property标签作用一样
    - 用于改变作用范围的：在bean标签中使用scope属性实现的功能是一样的
    - 和生命周期相关的：和bean标签中init-method和destory-method是一样的
  - 常用注解
    - Component 注解的作用是把当前类对象存入spring容器，属性value=bean中的id，默认值是当前的类名且首字母改小写,【下面三个和component的作用和属性一模一样】
      - controller:  一般用在表现层
      - service: 一般用于业务层，
      - repository: 一般用于持久层
    - Autowired
      - 类、方法
      - 自动按照类型注入，只要有唯一一个bean对象和要注入的变量类型匹配
      - qulifier和autowired一起使用，按照bean的Id注入
    - Resource
      - 直接按照Bean的Id注入，可以独立使用
    - Value：用于注入基本数据类型和String类型的数据，value用于指定数据的值
    - Scope：指定bean的作用范围，value：singletion prototype
    - predestory \ postConstructor
  - 存在于Jar包中的类，用xml配省事；如果类是自己写的，那么用注解省事
  - junit单元测试没有main方法也能执行，是集成了一个main方法。junit无论是否使用spring都可以用@Test去执行测试。所以需要导入spring-junit整合的jar包。
  - class类型是字节码，返回字节码。
- 第三天：spring中的aop和基于XML以及注解的AOP配置
- 第四天：spring中的JdbcTemplate以及spring事物控制
  - spring对JAVAEE api， JDBC，JAVAmail，远程调用进行封装，