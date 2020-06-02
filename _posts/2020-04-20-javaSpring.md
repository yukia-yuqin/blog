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
    
