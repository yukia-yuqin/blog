---
layout: post
title: Java spring
tags: java
categories: java
---
since 2020-01-05
spring boot <br>
<br>

### spring boot 
- spring 如何初始化? - web.xml
    - onstartup()方法七行代码（官方文档）
- dispatcher servlet如何注入给web的容器？ web.xml servlet
    - sm.xml干了什么？
        - 扫描。 /*yuqin 扫描什么呢?*/
        - 配置bean。
    - 这些功能都可以用onstartup中的annotation，appconfig程序替代。
    - tomcat用spi实现启动onstartup，而不是反射，因为反射还要Import到spring, tomcat是另一个公司的，不会这样做。dubbo中核心也是spi。
    - servlet 3.1规定在启动的时候一定会调用到webapplicationinitializer的onstartup方法

### spring aop（aspect oriented programming with spring）面向切面编程

- 应用
    - 什么叫做aop？
        - AOP是编程需要实现的目标，spring aop是手段，aspectJ也是一种实现方式。
        - 登陆，以传统面向对象，http->controller->service->dao，一些不影响主业务逻辑的方法(事物，异常，日志)叫做横切问题，面向切面编程关注执行的时机和执行的顺序。
    - 切面如何理解：
        - join point、point cut（连接点的集合）、target object（原来的对象）、proxy object（增强后的对象）、advise 增强的逻辑和增强的时机
        - 上述概念出现的那个类叫做切面
        - @Pointcut注解放在方法上，因为粒度不能放在类上，就放在方法上了。（excution）描述方法，（within）描述到类，（args）描述参数，（annotation），(this)
    - 自定义注解
    - spring framework 
        - 官网中 features 重要
    - reactive 技术栈
    - servlet 技术栈
    - 环绕通知？
        - around 可以对参数进行修改。
- 源码
    - spring aop原理
        - spring ioc和aop有什么关系
            - aop一定要放在ioc中
        - 目标对象什么时候被代理？
            - 初始化的时候
        - 目标对象去了哪里？
    - 如何看spring源码，调试源码
        - 带着问题看源码
        - 可以先认为某一些代码不用看，看它是否影响结果，影响再看。
        - 为什么会直接进到这一行，是因为上一行代码就直接进入了这一行。
        - spring中被实例化的单例对象基本都被存在Map中，getBean就是在一个concurrenthashmap中get一个对象。
        - createBean --> doCreateBean创建Bean--->initialBean代理
    - spring ioc后置处理器
    - jdk动态代理面试题目
        - jdk目标对象target object 和代理对象proxy object之间一定有一个转换的地方,就是getSingletion中的匿名方法实现了createBean()来创建原始对象和代理对象。
        - BeanDefination包含了class类型，通过反射得到一个对象
    - lookup-method 是ioc的知识。
   
- 微服务 spring cloud 框架分析
    - bean是什么？
    - 不要用低段位端口，容易和本身的http端口冲突，从1000开始用。
    - 负载均衡 nginx 没有消息是最好的消息 反向代理，用一个server的映射解决负载均衡。服务器端的负载均衡。upstream backser 反向代理。nginx不适于微服务的负载均衡。spring cloud中的负载均衡使用的是ribbon，在User service中加@LoadBalance就行。非常简单的一句。Nginx不能实现多种类型的微服务一起用。
    - spring cloud eureka

- spring bean的生命周期
    - spring-framework 在github上下载源码，在源码上开发，
    - 什么是spring
        - spring是一个公司，有许多项目。
    - 如何产生一个spring bean 和销毁一个spring bean
        - spring 中有一个工厂，产生bean的。
        - spring扫描，通过一个for循环，拿到很多类，解析类的名字。
        - 懒加载，@lazy注释
        - 过程：有一个beanDefinition,放入单例池，invokeBeanFactoryPostProccessors.
            - 扫描类，beanFactoryMap
            
### 鲁班学院java高级课程大纲
- 编程开发
    - 分布式netty
    - mybatis
    - tomcat
    - spring
    - spring boot
    - 并发编程框架akka
    - spring webflux
    - jdk新特性
- 运维部署
- 项目架构
- 性能调优
- 项目实战