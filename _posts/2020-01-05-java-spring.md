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