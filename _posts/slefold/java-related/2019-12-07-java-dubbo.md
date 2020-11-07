---
layout: post
title: dubbo
tags: study
categories: dailystudy
---

## 入门

## redis

- 磁盘太慢，内存太贵，产生redis
- redis完全由内存存储数据，不会和磁盘发生交换过程
- redis不是关系型数据库，因为关系型数据库需要是全量的，但是redis并不能是全量的，是热点数据存在redis中，所以数据类型是key value的
- redis面向用户的请求是单进程的，顺序执行的

## 【分布式存储】与【传统存储】的区别是什么？

- 软件定义存储，存储介质特别便宜，使用软件解决性能问题

### 背景

- 随着互联网的发展，网站应用的规模不断扩大，常规的垂直应用架构已无法应对，分布式服务架构以及流动计算架构势在必行，亟需一个治理系统确保架构有条不紊的演进。
apache dubbo 是一款高性能java RPC 框架。是阿里开发出来的，现在加到了apache里面去了。Apache Dubbo |ˈdʌbəʊ| 是一款高性能、轻量级的开源Java RPC框架，它提供了三大核心能力：面向接口的远程方法调用，智能容错和负载均衡(复杂)，以及服务自动注册和发现。高度可扩展能力。运行期流量调度。可视化的服务治理与运维。
RPC 远程过程调用（在面向对象里面==远程方法调用）
- [dubbo框架图][dubbo框架图]
- [手写模拟实现dubbo][手写模拟实现dubbo]

[dubbo框架图]:https://lh3.googleusercontent.com/4AkJgAKnnKNrJh8JwYwkecmJuW5YzSBklPP0Ur-xY89AiKMbabKeugUmwsU4ltV_mC3BzTckcwuumj2U0pxfhPfXKnky_pv9_gpBqw5zgqc-xFd1qb_q6CypZkEbuGR48v8yxKvppSXpvKymnPTqjqjwudjs1gVfZFAc3qQj_6mr8LELskvo4o6lnBir2qILfu8zxzARi2gQP0AhIAFPGCXNn45v4XDSEfMyt4kUBRx2EP8Ay994fCtBbqOxiQ3FeROhjhgSSMHF8DHF5fGuBHOLdFljvQ7T_wv1AqjeBEMLhiInhduw0_v95AnKx7wrZe70IpMFmvTuYhX_ZosrhYbJ5zSJfbVKxgR7k9uK9dcqjthXPz33LZ-F-ODI5n7mvyDiDcDM7-cvqKvXaTa2uwFj8LblVPy_lSAsTdfhVQvOC7Nue1vc196kxPcHyzXrvZzlv4DRotKUMgNItubZzgtQNuNeyuRfm5e-dshGgebzCF0NBNsg7NW50UnRJjjnMSRTXC4bKT_n5-xwwN_EFGFj_hGgD1LL4BaYTstpolRh2i1vPFMQFmnJKYCKJWbgrQoDuHe9AXTAs4W4b8nS94xaAabsJD9nj0yolq5PfWCKVQjPm6HQ7vv9PlpUb4d86rb49xEEtlwoKYzy22irXZ6umjX7fGA8ybuDd-vGCm7UkiGBJRZWYQ=w854-h525-no

[手写模拟实现dubbo]：https://lh3.googleusercontent.com/MAfZoJSdkc68nwyNm64HdDE1-HO0zO4HrRS9vjqUBbAZG78ZtrhmMiZ5OMnz3E_nyaQVUu7VkwqCuY_-ghmWAqKCwc8q3OiPg7fVC0E96SWsCLk19Vn1psu_NhRFZEZYajXFp2-5e8Gkw5OWltybM5X0m_5kNhyK9T6KHgGKeJ4r-YwzeVg_Up-LEB5Z2V4VqrVVIbGeF7RMbdLmFxE4tcb1X6uccy-wNz9I4xAVSVVY3bccERsQB5zx_vOYUlZbNgynWz7OfO0_ywT4a50yxHHMM-IvUEkRqq5eH--yZQ53E3M-pkSeAn11H6UoE3DZOeTBOXLWSi80FuaYTEwMH9Og3Uqld3VbcCDhqktkabXd3Df3Ax9ANVZwwDjSMIic3d48nmawGSD0bYZ_zvnCo2P3jXPjZXXV6Os5zsOIDdELfLrCg_y4uLgj05Sc6-xeCZc-BImwC9F8j-yuonDlDDMN_8One8OHtpUNkn_cD4VIzoU1PliD5gikNxssNppHJq8J5ukL_RPWm-hh5rNHG8FidrI3ey0fFGuBk9tSJUwdWnTCZpT7NBjPYJj0ln9yViUvhpZfPu14DsqLpuNvq0Vx14l9ZMsfQz-WRklmtC7S46gCIZo6xY-oenJ9xu_i0YE2Yy-0KiSYInIhv4nB6jXVsY1ZYRBzOAAEBe6kME-A68eOrWuf5Q=w699-h459-no

### 需求

### 架构

### 用法

## 快速启动

## 依赖

## 成熟度

## 配置

### XML配置

### 属性配置

### API配置

### 注解配置

#### 服务提供方

##### Service注解暴露服务@sevice

##### javaconfig形式配置公共模块@configuration、@bean

##### 指定dubbo扫描路径@springbootApplication、@DubboComponentScan

#### 服务消费方

##### Refrence注解引用服务

##### javaconfig形式配置公共模块

##### 指定dubbo扫描路径

## 示例

### 启动时检查

### 集群容错Cluster

#### failover重试、failfast快速失败、failsafe失败安全、failback失败自动恢复、forking并行调用多个服务器、broadcast广播调用所有提供者

#### 配置

##### 服务方<dubbo:reference cluster="failsafe" />

##### 消费方<dubbo:reference cluster="failsafe" />

### 负载均衡LoadBalance

#### Random随机、RoundRobin轮询、LeastActive最少活跃调用数、ConsistentHash一致性Hash

#### 配置

##### 服务端

###### 服务级别<dubbo:service interface="..." loadbalance="roundrobin" />

###### 方法级别<dubbo:service interface="...">    <dubbo:method name="..." loadbalance="roundrobin"/></dubbo:service>

##### 客户端

###### 服务级别<dubbo:reference interface="..." loadbalance="roundrobin" />

###### 方法级别<dubbo:reference interface="...">    <dubbo:method name="..." loadbalance="roundrobin"/></dubbo:reference>

### 线程模型

#### Dispatcher

##### all 所有消息都派发到线程池，包括请求，响应，连接事件，断开事件，心跳等

##### direct 所有消息都不派发到线程池，全部在 IO 线程上直接执行

##### message 只有请求响应消息派发到线程池，其它连接断开事件，心跳等消息，直接在 IO 线程上执行

##### execution 只请求消息派发到线程池，不含响应，响应和其它连接断开事件，心跳等消息，直接在 IO 线程上执行

##### connection 在 IO 线程上，将连接断开事件放入队列，有序逐个执行，其它消息派发到线程池

#### ThreadPool

##### fixed 固定大小线程池，启动时建立线程，不关闭，一直持有。(缺省)

##### cached 缓存线程池，空闲一分钟自动删除，需要时重建

##### limited 可伸缩线程池，但池中的线程数只会增长不会收缩。只增长不收缩的目的是为了避免收缩时突然来了大流量引起的性能问题

##### eager 优先创建Worker线程池

#### 配置

##### <dubbo:protocol name="dubbo" dispatcher="all" threadpool="fixed" threads="100" />

### 直连提供者

#### 应用场景

##### 绕过注册中心，只测试指定服务提供者

#### 解决方案

##### 点对点直联方式，以服务接口为单位，忽略注册中心的提供者列表

#### 配置

##### XML   <dubbo:reference id="xxxService" interface="com.alibaba.xxx.XxxService" url="dubbo://localhost:20890" />

##### -D参数指定   java -Dcom.alibaba.xxx.XxxService=dubbo://localhost:20890

##### 文件映射

###### 1 建立.properties文件，添加   com.alibaba.xxx.XxxService=dubbo://localhost:20890

###### 2 指定映射文件路径   java -Ddubbo.resolve.file=xxx.properties

### 只订阅

#### 应用场景

##### 为方便开发测试，经常会在线下共用一个所有服务可用的注册中心，这时，如果一个正在开发中的服务提供者注册，可能会影响消费者不能正常运行

#### 解决方案

##### 可以让服务提供者开发方，只订阅服务(开发的服务可能依赖其它服务)，而不注册正在开发的服务，通过直连测试正在开发的服务

#### 禁用注册配置（二者选一）

##### <dubbo:registry address="10.20.153.10:9090" register="false" />

##### <dubbo:registry address="10.20.153.10:9090?register=false" />

### 只注册

#### 应用场景

##### 如果有两个镜像环境，两个注册中心，有一个服务只在其中一个注册中心有部署，另一个注册中心还没来得及部署，而两个注册中心的其它应用都需要依赖此服务

#### 解决方案

##### 可以让服务提供者方只注册服务到另一注册中心，而不从另一注册中心订阅服务

#### 禁用订阅配置（二者选一）

##### <dubbo:registry id="hzRegistry" address="10.20.153.10:9090" />
<dubbo:registry id="qdRegistry" address="10.20.141.150:9090" subscribe="false" />

##### <dubbo:registry id="hzRegistry" address="10.20.153.10:9090" />
<dubbo:registry id="qdRegistry" address="10.20.141.150:9090?subscribe=false" />

### 静态服务

#### 应用场景

##### 希望人工管理服务提供者的上线和下线

#### 解决方案

##### 将注册中心标识为非动态管理模式

#### 配置（二者选一）

##### <dubbo:registry address="10.20.141.150:9090" dynamic="false" />

##### <dubbo:registry address="10.20.141.150:9090?dynamic=false" />

### 多协议

#### 概念

##### 在不同服务上支持不同协议或者同一服务上同时支持多种协议

#### 配置

##### 不同服务不同协议

######  <!-- 多协议配置 -->
    <dubbo:protocol name="dubbo" port="20880" />
    <dubbo:protocol name="rmi" port="1099" />
    <!-- 使用dubbo协议暴露服务 -->
    <dubbo:service interface="com.alibaba.hello.api.HelloService" version="1.0.0" ref="helloService" protocol="dubbo" />
    <!-- 使用rmi协议暴露服务 -->
    <dubbo:service interface="com.alibaba.hello.api.DemoService" version="1.0.0" ref="demoService" protocol="rmi" /> 

##### 多协议暴露服务

###### <!-- 多协议配置 -->
    <dubbo:protocol name="dubbo" port="20880" />
    <dubbo:protocol name="hessian" port="8080" />
    <!-- 使用多个协议暴露服务 -->
    <dubbo:service id="helloService" interface="com.alibaba.hello.api.HelloService" version="1.0.0" protocol="dubbo,hessian" />

### 多注册中心

#### 概念

##### Dubbo 支持同一服务向多注册中心同时注册，或者不同服务分别注册到不同的注册中心上去，甚至可以同时引用注册在不同注册中心上的同名服务

#### 形式

##### 多注册中心注册

###### 场景

####### 比如：中文站有些服务来不及在青岛部署，只在杭州部署，而青岛的其它应用需要引用此服务，就可以将服务同时注册到两个注册中心

###### 配置

####### <!-- 多注册中心配置 -->
    <dubbo:registry id="hangzhouRegistry" address="10.20.141.150:9090" />
    <dubbo:registry id="qingdaoRegistry" address="10.20.141.151:9010" default="false" />
    <!-- 向多个注册中心注册 -->
    <dubbo:service interface="com.alibaba.hello.api.HelloService" version="1.0.0" ref="helloService" registry="hangzhouRegistry,qingdaoRegistry" />

##### 不同服务使用不同注册中心

###### 场景

####### 比如：CRM 有些服务是专门为国际站设计的，有些服务是专门为中文站设计的

###### 配置

####### <!-- 多注册中心配置 -->
    <dubbo:registry id="chinaRegistry" address="10.20.141.150:9090" />
    <dubbo:registry id="intlRegistry" address="10.20.154.177:9010" default="false" />
    <!-- 向中文站注册中心注册 -->
    <dubbo:service interface="com.alibaba.hello.api.HelloService" version="1.0.0" ref="helloService" registry="chinaRegistry" />
    <!-- 向国际站注册中心注册 -->
    <dubbo:service interface="com.alibaba.hello.api.DemoService" version="1.0.0" ref="demoService" registry="intlRegistry" />

##### 多注册中心引用

###### 场景

####### 比如：CRM 需同时调用中文站和国际站的 PC2 服务，PC2 在中文站和国际站均有部署，接口及版本号都一样，但连的数据库不一样

###### 配置

####### <!-- 多注册中心配置 -->
    <dubbo:registry id="chinaRegistry" address="10.20.141.150:9090" />
    <dubbo:registry id="intlRegistry" address="10.20.154.177:9010" default="false" />
    <!-- 引用中文站服务 -->
    <dubbo:reference id="chinaHelloService" interface="com.alibaba.hello.api.HelloService" version="1.0.0" registry="chinaRegistry" />
    <!-- 引用国际站站服务 -->
    <dubbo:reference id="intlHelloService" interface="com.alibaba.hello.api.HelloService" version="1.0.0" registry="intlRegistry" />

### 服务分组

#### 应用场景

##### 当一个接口有多种实现时，可以用 group 区分

#### 配置

##### 服务

###### <dubbo:service group="feedback" interface="com.xxx.IndexService" />
<dubbo:service group="member" interface="com.xxx.IndexService" />

##### 引用

###### <dubbo:reference id="feedbackIndexService" group="feedback" interface="com.xxx.IndexService" />
<dubbo:reference id="memberIndexService" group="member" interface="com.xxx.IndexService" />

##### 任意组

###### <dubbo:reference id="barService" interface="com.foo.BarService" group="*" />

### 多版本

#### 应用场景

##### 当一个接口实现，出现不兼容升级时，可以用版本号过渡，版本号不同的服务相互间不引用

#### 步骤

##### 1 在低压力时间段，先升级一半提供者为新版本
2 再将所有消费者升级为新版本
3 然后将剩下的一半提供者升级为新版本

#### 配置

##### 老版本

###### 服务提供者   <dubbo:service interface="com.foo.BarService" version="1.0.0" />

###### 服务消费者   <dubbo:reference id="barService" interface="com.foo.BarService" version="1.0.0" />

##### 新版本

###### 服务提供者   <dubbo:service interface="com.foo.BarService" version="2.0.0" />

###### 服务消费者   <dubbo:reference id="barService" interface="com.foo.BarService" version="2.0.0" />

##### 不需区分版本   <dubbo:reference id="barService" interface="com.foo.BarService" version="*" />

### 分组聚合

#### 应用场景

##### 按组合并返回结果，比如菜单服务，接口一样，但有多种实现，用group区分，现在消费方需从每种group中调用一次返回结果，合并结果返回，这样就可以实现聚合菜单项

#### 配置

##### 搜索所有分组   <dubbo:reference interface="com.xxx.MenuService" group="*" merger="true" />

##### 合并指定分组   <dubbo:reference interface="com.xxx.MenuService" group="aaa,bbb" merger="true" />

##### 制定方法合并结果，其它未指定的方法，将只调用一个 Group   
<dubbo:reference interface="com.xxx.MenuService" group="*">    <dubbo:method name="getMenuItems" merger="true" /></dubbo:service>

##### 某个方法不合并结果，其它都合并结果   
<dubbo:reference interface="com.xxx.MenuService" group="*" merger="true">    <dubbo:method name="getMenuItems" merger="false" /></dubbo:service>

##### 指定合并策略，缺省根据返回值类型自动匹配，如果同一类型有两个合并器时，需指定合并器的名称
<dubbo:reference interface="com.xxx.MenuService" group="*">    <dubbo:method name="getMenuItems" merger="mymerge" /></dubbo:service>

##### 指定合并方法，将调用返回结果的指定方法进行合并，合并方法的参数类型必须是返回结果类型本身
<dubbo:reference interface="com.xxx.MenuService" group="*">    <dubbo:method name="getMenuItems" merger=".addAll" /></dubbo:service>

### 参数验证

#### 概念

##### 参数验证功能 是基于 JSR303实现的，用户只需标识 JSR303 标准的验证 annotation，并通过声明 filter 来实现验证

#### Maven依赖

##### <dependency>
    <groupId>javax.validation</groupId>
    <artifactId>validation-api</artifactId>
    <version>1.0.0.GA</version>
</dependency>
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-validator</artifactId>
    <version>4.2.0.Final</version></dependency>

#### 示例

##### 参数标注示例

######  @NotNull // 不允许为空
    @Size(min = 1, max = 20) // 长度或大小范围
    private String name;

##### 分组验证示例

###### public interface ValidationService { // 缺省可按服务接口区分验证场景，如：@NotNull(groups = ValidationService.class) 
	@interface Save{} // 与方法同名接口，首字母大写，用于区分验证场景，如：@NotNull(groups = ValidationService.Save.class)，可选
	void save(ValidationParameter parameter);
void update(ValidationParameter parameter);
}

##### 关联验证示例

###### public interface ValidationService {   
	@GroupSequence(Update.class) // 同时验证Update组规则    @interface Save{}
	void save(ValidationParameter parameter);
	@interface Update{} 
	void update(ValidationParameter parameter);
}

##### 参数验证示例

###### public interface ValidationService {
	void save(@NotNull ValidationParameter parameter); // 验证参数不为空void delete(@Min(1) int id); // 直接对基本类型参数验证
}

#### 配置

##### 客户端   <dubbo:reference id="validationService" interface="com.alibaba.dubbo.examples.validation.api.ValidationService" validation="true" />

##### 服务端   <dubbo:service interface="com.alibaba.dubbo.examples.validation.api.ValidationService" ref="validationService" validation="true" />

### 结果缓存

#### 概念

##### 结果缓存，用于加速热门数据的访问速度，Dubbo 提供声明式缓存，以减少用户加缓存的工作量

#### 缓存类型

##### lru 基于最近最少使用原则删除多余缓存，保持最热的数据被缓存

##### threadlocal 当前线程缓存，比如一个页面渲染，用到很多 portal，每个 portal 都要去查用户信息，通过线程缓存，可以减少这种多余访问

##### jcache 与 JSR107 集成，可以桥接各种缓存实现

#### 配置（二者选一）

##### <dubbo:reference interface="com.foo.BarService" cache="lru" />

##### <dubbo:reference interface="com.foo.BarService">    <dubbo:method name="findBar" cache="lru" /></dubbo:reference>

### 泛化引用

#### 概念

##### 泛化接口调用方式主要用于客户端没有 API 接口及模型类元的情况，参数及返回值中的所有 POJO 均用 Map 表示，通常用于框架集成

#### 通过Spring使用泛化调用

##### 配置   

###### <dubbo:reference id="barService" interface="com.foo.BarService" generic="true" />

##### java使用barService进行泛化调用

###### GenericService barService = (GenericService) applicationContext.getBean("barService");
Object result = barService.$invoke("sayHello", new String[] { "java.lang.String" }, new Object[] { "World" });

### 泛化实现

#### 概念

##### 泛接口实现方式主要用于服务器端没有API接口及模型类元的情况，参数及返回值中的所有POJO均用Map表示，通常用于框架集成

#### java代码实现GenericService 接口

##### public class MyGenericService implements GenericService {
	public Object $invoke(String methodName, String[] parameterTypes, Object[] args) throws GenericException {
	    if ("sayHello".equals(methodName)) {
	        return "Welcome " + args[0];}}
}

#### 通过 Spring 暴露泛化实现

##### <bean id="genericService" class="com.foo.MyGenericService" />
<dubbo:service interface="com.foo.BarService" ref="genericService" />

### 回声测试

#### 概念

##### 回声测试用于检测服务是否可用，回声测试按照正常请求流程执行，能够测试整个调用是否通畅，可用于监控

#### 机制

##### 所有服务自动实现 EchoService 接口，只需将任意服务引用强制转型为 EchoService，即可使用

#### 配置

##### <dubbo:reference id="memberService" interface="com.xxx.MemberService" />

#### 示例

##### // 远程服务引用
MemberService memberService = ctx.getBean("memberService"); 
EchoService echoService = (EchoService) memberService; // 强制转型为EchoService
// 回声测试可用性
String status = echoService.$echo("OK"); 
assert(status.equals("OK"));

### 上下文信息

#### 概念

##### 上下文中存放的是当前调用过程中所需的环境信息，所有配置信息都将转换为 URL 的参数

#### 机制

##### RpcContext 是一个 ThreadLocal 的临时状态记录器，当接收到 RPC 请求，或发起 RPC 请求时，RpcContext 
的状态都会变化。比如：A 调 B，B 再调 C，则 B 机器上，在 B 调 C 之前，RpcContext 记录的是 A 调 B 的信息，在 B
 调 C 之后，RpcContext 记录的是 B 调 C 的信息

#### 示例

##### 服务消费方

###### // 远程调用
xxxService.xxx();
// 本端是否为消费端，这里会返回trueboolean isConsumerSide = RpcContext.getContext().isConsumerSide();
// 获取最后一次调用的提供方IP地址
String serverIP = RpcContext.getContext().getRemoteHost();
// 获取当前服务配置信息，所有配置信息都将转换为URL的参数
String application = RpcContext.getContext().getUrl().getParameter("application");
// 注意：每发起RPC调用，上下文状态会变化
yyyService.yyy();

##### 服务提供方

###### public class XxxServiceImpl implements XxxService {
	public void xxx() {
	    // 本端是否为提供端，这里会返回true        boolean isProviderSide = RpcContext.getContext().isProviderSide();
	    // 获取调用方IP地址
	    String clientIP = RpcContext.getContext().getRemoteHost();
	    // 获取当前服务配置信息，所有配置信息都将转换为URL的参数
	    String application = RpcContext.getContext().getUrl().getParameter("application");
	    // 注意：每发起RPC调用，上下文状态会变化
	    yyyService.yyy();
	    // 此时本端变成消费端，这里会返回false        boolean isProviderSide = RpcContext.getContext().isProviderSide();
	} 
}

### 隐式参数

#### 机制

##### 可以通过 RpcContext 上的 setAttachment 和 getAttachment 在服务消费方和提供方之间进行参数的隐式传递

#### 实现

##### 分支主题

###### 在服务消费方端设置隐式参数

####### RpcContext.getContext().setAttachment("index", "1"); // 隐式传参，后面的远程调用都会隐式将这些参数发送到服务器端，类似cookie，用于框架集成，不建议常规业务使用
xxxService.xxx(); // 远程调用

###### 在服务提供方端获取隐式参数

####### public class XxxServiceImpl implements XxxService {
	public void xxx() {
	    // 获取客户端隐式传入的参数，用于框架集成，不建议常规业务使用
	    String index = RpcContext.getContext().getAttachment("index"); 
	}
}

#### 注意

##### 注意：path, group, version, dubbo, token, timeout 几个 key 是保留字段，请使用其它值

### 异步调用

#### 意义

##### 基于 NIO 的非阻塞实现并行调用，客户端不需要启动多线程即可完成并行调用多个远程服务，相对多线程开销较小

#### 配置consumer.xml

##### <dubbo:reference id="fooService" interface="com.alibaba.foo.FooService">
<dubbo:method name="findFoo" async="true" />
</dubbo:reference>
<dubbo:reference id="barService" interface="com.alibaba.bar.BarService"> 
 <dubbo:method name="findBar" async="true" />
</dubbo:reference>

#### 调用代码

##### // 此调用会立即返回null
fooService.findFoo(fooId);
// 拿到调用的Future引用，当结果返回后，会被通知和设置到此Future
Future<Foo> fooFuture = RpcContext.getContext().getFuture(); 
// 此调用会立即返回null
barService.findBar(barId);
// 拿到调用的Future引用，当结果返回后，会被通知和设置到此Future
Future<Bar> barFuture = RpcContext.getContext().getFuture(); 
// 此时findFoo和findBar的请求同时在执行，客户端不需要启动多线程来支持并行，而是借助NIO的非阻塞完成
 // 如果foo已返回，直接拿到返回值，否则线程wait住，等待foo返回后，线程会被notify唤醒
Foo foo = fooFuture.get(); 
// 同理等待bar返回
Bar bar = barFuture.get(); 
// 如果foo需要5秒返回，bar需要6秒返回，实际只需等6秒，即可获取到foo和bar，进行接下来的处理。

#### 其他设置

##### 设置是否等待消息发出

###### sent="true" 等待消息发出，消息发送失败将抛出异常。
sent="false" 不等待消息发出，将消息放入 IO 队列，即刻返回

####### <dubbo:method name="findFoo" async="true" sent="true" />

##### 如果你只是想异步，完全忽略返回值，可以配置 return="false"，以减少 Future 对象的创建和管理成本

###### <dubbo:method name="findFoo" async="true" return="false" />

### 本地调用

#### 概念

##### 本地调用使用了 injvm 协议，是一个伪协议，它不开启端口，不发起远程调用，只在 JVM 内直接关联，但执行 Dubbo 的 Filter 链

#### 配置

##### 定义 injvm 协议

###### <dubbo:protocol name="injvm" />

##### 设置默认协议

###### <dubbo:provider protocol="injvm" />

##### 设置服务协议

###### <dubbo:service protocol="injvm" />

##### 优先使用 injvm（二者选一）

###### <dubbo:consumer injvm="true" .../><dubbo:provider injvm="true" .../>

###### <dubbo:reference injvm="true" .../><dubbo:service injvm="true" .../>

##### 注意：服务暴露与服务引用都需要声明 injvm="true"

#### 自动暴露、引用本地服务

##### 应用场景

###### 从 2.2.0 开始，每个服务默认都会在本地暴露。在引用服务的时候，默认优先引用本地服务。如果希望引用远程服务可以使用一下配置强制引用远程服务。

##### 配置

###### <dubbo:reference ... scope="remote" />

### 参数回调

#### 概念

##### 参数回调方式与调用本地 callback 或 listener 相同，只需要在 Spring 的配置文件中声明哪个参数是 callback 类型即可。
Dubbo 将基于长连接生成反向代理，这样就可以从服务器端调用客户端逻辑 

#### 示例

##### 参见 http://dubbo.apache.org/#!/docs/user/demos/callback-parameter.md?lang=zh-cn

### 事件通知

#### 概念

##### 在调用之前、调用之后、出现异常时，会触发 oninvoke、onreturn、onthrow 三个事件，可以配置当事件发生时，通知哪个类的哪个方法

#### 示例

##### 参照   http://dubbo.apache.org/#!/docs/user/demos/events-notify.md?lang=zh-cn

### 本地存根

#### 应用场景

##### 远程服务后，客户端通常只剩下接口，而实现全在服务器端，但提供方有些时候想在客户端也执行部分逻辑，
比如：做 ThreadLocal 缓存，提前验证参数，调用失败后伪造容错数据等等

#### 解决方案

##### 在 API 中带上 Stub，客户端生成 Proxy 实例，会把 Proxy 通过构造函数传给 Stub ，然后把 Stub 暴露给用户，Stub 可以决定要不要去调 Proxy

#### 配置（二者选一）

##### <dubbo:service interface="com.foo.BarService" stub="true" />

##### <dubbo:service interface="com.foo.BarService" stub="com.foo.BarServiceStub" />

### 本地伪装

#### 概念

##### 本地伪装通常用于服务降级，比如某验权服务，当服务提供方全部挂掉后，客户端不抛出异常，而是通过 Mock 数据返回授权失败

#### 配置（二者选一）

##### <dubbo:reference interface="com.foo.BarService" mock="true" />

##### <dubbo:reference interface="com.foo.BarService" mock="com.foo.BarServiceMock" />

#### 如若只想简单忽略异常

##### <dubbo:reference interface="com.foo.BarService" mock="return null" />

### 延迟暴露

#### 概念

##### 如果你的服务需要预热时间，比如初始化缓存，等待相关资源就位等，可以使用 delay 进行延迟暴露

#### 配置

##### 延迟5秒暴露服务

###### <dubbo:service delay="5000" />

##### 延迟到Spring初始化完成

###### <dubbo:service delay="-1" />

### 并发控制

#### 示例1

##### 说明

###### 限制 com.foo.BarService 的每个方法，服务器端并发执行（或占用线程池线程数）不能超过 10 个

##### 配置

###### <dubbo:service interface="com.foo.BarService" executes="10" />

#### 示例2

##### 说明

###### 限制 com.foo.BarService 的 sayHello 方法，服务器端并发执行（或占用线程池线程数）不能超过 10 个

##### 配置

###### <dubbo:service interface="com.foo.BarService">    <dubbo:method name="sayHello" executes="10" /></dubbo:service>

#### 示例3

##### 说明

###### 限制 com.foo.BarService 的每个方法，每客户端并发执行（或占用连接的请求数）不能超过 10 个

##### 配置

###### <dubbo:service interface="com.foo.BarService" actives="10" />

###### <dubbo:reference interface="com.foo.BarService" actives="10" />

#### 示例4

##### 说明

###### 限制 com.foo.BarService 的 sayHello 方法，每客户端并发执行（或占用连接的请求数）不能超过 10 个

##### 配置

###### <dubbo:service interface="com.foo.BarService">    <dubbo:method name="sayHello" actives="10" /></dubbo:service>

###### <dubbo:reference interface="com.foo.BarService">    <dubbo:method name="sayHello" actives="10" /></dubbo:service>

###### 如果 <dubbo:service> 和 <dubbo:reference> 都配了actives，<dubbo:reference> 优先

#### Load Balance 均衡

##### 说明

###### 配置服务的客户端的 loadbalance 属性为 leastactive，此 Loadbalance 会调用并发数最小的 Provider（Consumer端并发数）

##### 配置

###### <dubbo:reference interface="com.foo.BarService" loadbalance="leastactive" />

###### <dubbo:service interface="com.foo.BarService" loadbalance="leastactive" />

### 连接控制

#### 服务端连接控制

##### 限制服务器端接受的连接不能超过 10 个

###### <dubbo:provider protocol="dubbo" accepts="10" />

###### <dubbo:protocol name="dubbo" accepts="10" />

#### 客户端连接控制

##### 限制客户端服务使用连接不能超过 10 个

###### <dubbo:reference interface="com.foo.BarService" connections="10" />

###### <dubbo:service interface="com.foo.BarService" connections="10" />

### 延迟连接

#### 概念

##### 延迟连接用于减少长连接数。当有调用发起时，再创建长连接

#### 配置

##### <dubbo:protocol name="dubbo" lazy="true" />

#### 注意：该配置只对使用长连接的 dubbo 协议生效

### 粘滞连接

#### 概念

##### 粘滞连接用于有状态服务，尽可能让客户端总是向同一提供者发起调用，除非该提供者挂了，再连另一台。
粘滞连接将自动开启延迟连接
，以减少长连接数

#### 配置

##### <dubbo:protocol name="dubbo" sticky="true" />

### 令牌验证

#### 概念

##### 通过令牌验证在注册中心控制权限，以决定要不要下发令牌给消费者，可以防止消费者绕过注册中心访问提供者，另外通过注册中心可灵活改变授权方式，而不需修改或升级提供者

#### 配置

##### 全局设置

###### <!--随机token令牌，使用UUID生成--><dubbo:provider interface="com.foo.BarService" token="true" />

###### <!--固定token令牌，相当于密码--><dubbo:provider interface="com.foo.BarService" token="123456" />

##### 服务级别设置

###### <!--随机token令牌，使用UUID生成--><dubbo:service interface="com.foo.BarService" token="true" />

###### <!--固定token令牌，相当于密码--><dubbo:service interface="com.foo.BarService" token="123456" />

##### 协议级别设置

###### <!--随机token令牌，使用UUID生成--><dubbo:protocol name="dubbo" token="true" />

###### <!--固定token令牌，相当于密码--><dubbo:protocol name="dubbo" token="123456" />

###  

#### 概念

##### 路由规则决定一次 dubbo 服务调用的目标服务器，分为条件路由规则和脚本路由规则，并且支持可扩展

#### 写入路由规则

##### 向注册中心写入路由规则的操作通常由监控中心或治理中心的页面完成

##### RegistryFactory registryFactory = ExtensionLoader.getExtensionLoader(RegistryFactory.class).getAdaptiveExtension();
Registry registry = registryFactory.getRegistry(URL.valueOf("zookeeper://10.20.153.10:2181"));
registry.register(URL.valueOf("condition://0.0.0.0/com.foo.BarService?category=routers&dynamic=false&rule=" + URL.encode("host = 10.20.153.10 => host = 10.20.153.11") + "));

##### 各字段含义

###### condition:// 表示路由规则的类型，支持条件路由规则和脚本路由规则，可扩展，必填。
0.0.0.0 表示对所有 IP 地址生效，如果只想对某个 IP 的生效，请填入具体 IP，必填。
com.foo.BarService 表示只对指定服务生效，必填。
group=foo 对指定服务的指定group生效，不填表示对未配置group的指定服务生效
version=1.0对指定服务的指定version生效，不填表示对未配置version的指定服务生效
category=routers 表示该数据为动态配置类型，必填。
dynamic=false 表示该数据为持久数据，当注册方退出时，数据依然保存在注册中心，必填。
enabled=true 覆盖规则是否生效，可不填，缺省生效。
force=false 当路由结果为空时，是否强制执行，如果不强制执行，路由结果为空的路由规则将自动失效，可不填，缺省为 false。
runtime=false 是否在每次调用时执行路由规则，否则只在提供者地址列表变更时预先执行并缓存结果，调用时直接从缓存中获取路由结果。如果用了参数路由，必须设为 true，需要注意设置会影响调用的性能，可不填，缺省为 false。
priority=1 路由规则的优先级，用于排序，优先级越大越靠前执行，可不填，缺省为 0。
rule=URL.encode("host = 10.20.153.10 => host = 10.20.153.11") 表示路由规则的内容，必填

#### 条件路由规则

##### 形式

###### 基于条件表达式的路由规则，如：host = 10.20.153.10 => host = 10.20.153.11

##### 规则

###### => 之前的为消费者匹配条件，所有参数和消费者的 URL 进行对比，当消费者满足匹配条件时，对该消费者执行后面的过滤规则。
=> 之后为提供者地址列表的过滤条件，所有参数和提供者的 URL 进行对比，消费者最终只拿到过滤后的地址列表。
如果匹配条件为空，表示对所有消费方应用，如：=> host != 10.20.153.11
如果过滤条件为空，表示禁止访问，如：host = 10.20.153.10 =>

##### 表达式

###### 参数支持

####### 服务调用信息，如：method, argument 等，暂不支持参数路由
URL 本身的字段，如：protocol, host, port 等
以及 URL 上的所有参数，如：application, organization 等

###### 条件支持

####### 等号 = 表示"匹配"，如：host = 10.20.153.10
不等号 != 表示"不匹配"，如：host != 10.20.153.10

###### 值支持

####### 以逗号 , 分隔多个值，如：host != 10.20.153.10,10.20.153.11
以星号 * 结尾，表示通配，如：host != 10.20.*
以美元符 $ 开头，表示引用消费者参数，如：host = $host

##### 脚本路由规则

### 配置规则

#### 向注册中心写入动态配置覆盖规则，该功能通常由监控中心或治理中心的页面完成

#### RegistryFactory registryFactory = ExtensionLoader.getExtensionLoader(RegistryFactory.class).getAdaptiveExtension();
Registry registry = registryFactory.getRegistry(URL.valueOf("zookeeper://10.20.153.10:2181"));
registry.register(URL.valueOf("override://0.0.0.0/com.foo.BarService?category=configurators&dynamic=false&application=foo&timeout=1000"));

#### 各字段含义

##### override:// 表示数据采用覆盖方式，支持 override 和 absent，可扩展，必填。
0.0.0.0 表示对所有 IP 地址生效，如果只想覆盖某个 IP 的数据，请填入具体 IP，必填。
com.foo.BarService 表示只对指定服务生效，必填。
category=configurators 表示该数据为动态配置类型，必填。
dynamic=false 表示该数据为持久数据，当注册方退出时，数据依然保存在注册中心，必填。
enabled=true 覆盖规则是否生效，可不填，缺省生效。
application=foo 表示只对指定应用生效，可不填，表示对所有应用生效。
timeout=1000 表示将满足以上条件的 timeout 参数的值覆盖为 1000。如果想覆盖其它参数，直接加在 override 的 URL 参数上。

#### 示例

##### 示例1

###### 禁用提供者：(通常用于临时踢除某台提供者机器，相似的，禁止消费者访问请使用路由规则)

###### override://10.20.153.10/com.foo.BarService?category=configurators&dynamic=false&disbaled=true

##### 示例2

###### 调整权重：(通常用于容量评估，缺省权重为 100)

###### override://10.20.153.10/com.foo.BarService?category=configurators&dynamic=false&weight=200

##### 示例3

###### 调整负载均衡策略：(缺省负载均衡策略为 random)

###### override://10.20.153.10/com.foo.BarService?category=configurators&dynamic=false&loadbalance=leastactive

##### 示例4

###### 服务降级：(通常用于临时屏蔽某个出错的非关键服务)

###### override://0.0.0.0/com.foo.BarService?category=configurators&dynamic=false&application=foo&mock=force:return+null

### 服务降级

#### 可以通过服务降级功能临时屏蔽某个出错的非关键服务，并定义降级后的返回策略

#### RegistryFactory registryFactory = ExtensionLoader.getExtensionLoader(RegistryFactory.class).getAdaptiveExtension();
Registry registry = registryFactory.getRegistry(URL.valueOf("zookeeper://10.20.153.10:2181"));
registry.register(URL.valueOf("override://0.0.0.0/com.foo.BarService?category=configurators&dynamic=false&application=foo&mock=force:return+null"));

#### 各字段含义

##### mock=force:return+null 表示消费方对该服务的方法调用都直接返回 null 值，不发起远程调用。用来屏蔽不重要服务不可用时对调用方的影响。
还可以改为 mock=fail:return+null 表示消费方对该服务的方法调用在失败后，再返回 null 值，不抛异常。用来容忍不重要服务不稳定时对调用方的影响。

### 优雅停机

#### 概念

##### Dubbo 是通过 JDK 的 ShutdownHook 来完成优雅停机的，所以如果用户使用 kill -9 PID 等强制关闭指令，是不会执行优雅停机的，只有通过 kill PID 时，才会执行

#### 原理

##### 服务提供方

###### 停止时，先标记为不接收新请求，新请求过来时直接报错，让客户端重试其它机器。
然后，检测线程池中的线程是否正在运行，如果有，等待所有线程执行完成，除非超时，则强制关闭

##### 服务消费方

###### 停止时，不再发起新的调用请求，所有新的调用在客户端即报错。
然后，检测有没有请求的响应还没有返回，等待响应返回，除非超时，则强制关闭。

#### 设置方式

##### 设置优雅停机超时时间，缺省超时时间是 10 秒，如果超时则强制关闭

###### # dubbo.properties
dubbo.service.shutdown.wait=15000

##### 如果 ShutdownHook 不能生效，可以自行调用，使用tomcat等容器部署的場景，建议通过扩展ContextListener等自行调用以下代码实现优雅停机

###### ProtocolConfig.destroyAll();

### 主机绑定

#### 查找顺序

##### 通过 LocalHost.getLocalHost() 获取本机地址。
如果是 127.* 等 loopback 地址，则扫描各网卡，获取网卡 IP

#### 主机配置

##### 应用场景

###### 注册的地址如果获取不正确，比如需要注册公网地址

##### 解决方案（选一）

###### 可以在 /etc/hosts 中加入：机器名 公网 IP，比如：test1 205.182.23.201

###### 在 dubbo.xml 中加入主机地址的配置：<dubbo:protocol host="205.182.23.201">

###### 或在 dubbo.properties 中加入主机地址的配置：dubbo.protocol.host=205.182.23.201

#### 端口配置

##### 协议-端口

###### dubbo-20880；rmi-1099；http-80；hessian-80；webservice-80；memcached-11211；redis-6379

##### 配置

###### 在 dubbo.xml 中加入主机地址的配置   <dubbo:protocol name="dubbo" port="20880">

###### 或在 dubbo.properties 中加入主机地址的配置   dubbo.protocol.dubbo.port=20880

### 日志匹配

#### 背景

##### 自 2.2.1 开始，dubbo 开始内置 log4j、slf4j、jcl、jdk 这些日志框架的适配 

#### 显示配置日志输出策略

##### 命令行   java -Ddubbo.application.logger=log4j

##### 在 `dubbo.properties` 中指定   dubbo.application.logger=log4j

##### 在 dubbo.xml 中配置   <dubbo:application logger="log4j" />

### 访问日志

#### 说明

##### 如果你想记录每一次请求信息，可开启访问日志，类似于apache的访问日志。注意：此日志量比较大，请注意磁盘容量

#### 配置

##### 将访问日志输出到当前应用的log4j日志： <dubbo:protocol accesslog="true" />

##### 将访问日志输出到指定文件： <dubbo:protocol accesslog="http://10.20.160.198/wiki/display/dubbo/foo/bar.log" />

### 服务容器

#### 说明

##### 1. 服务容器是一个 standalone 的启动程序，因为后台服务不需要 Tomcat 或 JBoss 等 Web 容器的功能，如果硬要用 Web 容器去加载服务提供方，增加复杂性，也浪费资源

##### 2. 服务容器只是一个简单的 Main 方法，并加载一个简单的 Spring 容器，用于暴露服务

##### 3. 服务容器的加载内容可以扩展，内置了 spring, jetty, log4j 等加载，可通过容器扩展点进行扩展。配置配在 java 命令的 -D 参数或者 dubbo.properties 中

#### 容器类型

##### Spring Container

###### 自动加载 META-INF/spring 目录下的所有 Spring 配置

###### 配置 spring 配置加载位置

####### dubbo.spring.config=classpath*:META-INF/spring/*.xml

##### Jetty Container

###### 启动一个内嵌 Jetty，用于汇报状态

###### 配置

####### `dubbo.jetty.port=8080`：配置 jetty 启动端口

####### `dubbo.jetty.directory=/foo/bar`：配置可通过 jetty 直接访问的目录，用于存放静态文件

####### `dubbo.jetty.page=log,status,system`：配置显示的页面，缺省加载所有页面

##### Log4j Container

###### 自动配置 log4j 的配置，在多进程启动时，自动给日志文件按进程分目录

###### 配置

####### `dubbo.log4j.file=/foo/bar.log`：配置日志文件路径

####### `dubbo.log4j.level=WARN`：配置日志级别

####### `dubbo.log4j.subdirectory=20880`：配置日志子目录，用于多进程启动，避免冲突

#### 容器启动

##### 缺省只加载Spring

##### 配置

###### 通过 main 函数参数传入要加载的容器：java com.alibaba.dubbo.container.Main spring jetty log4j

###### 通过 JVM 启动参数传入要加载的容器：java com.alibaba.dubbo.container.Main -Ddubbo.container=spring,jetty,log4j

###### 通过 classpath 下的 dubbo.properties 配置传入要加载的容器：dubbo.container=spring,jetty,log4j

### ReferenceConfig 缓存

#### 背景

##### ReferenceConfig 实例很重，封装了与注册中心的连接以及与提供者的连接，需要缓存。否则重复生成 ReferenceConfig 可能造成性能问题并且会有内存和连接泄漏。在 API 方式编程时，容易忽略此问题

#### 解决方案

##### 自 2.4.0 版本开始， dubbo 提供了简单的工具类 ReferenceConfigCache用于缓存 ReferenceConfig 实例

#### 使用方式

##### ReferenceConfig<XxxService> reference = new ReferenceConfig<XxxService>();
reference.setInterface(XxxService.class);
reference.setVersion("1.0.0");
......
ReferenceConfigCache cache = ReferenceConfigCache.getCache();
// cache.get方法中会缓存 Reference对象，并且调用ReferenceConfig.get方法启动ReferenceConfig
XxxService xxxService = cache.get(reference);
// 注意！ Cache会持有ReferenceConfig，不要在外部再调用ReferenceConfig的destroy方法，导致Cache内的ReferenceConfig失效！
// 使用xxxService对象
xxxService.sayHello();

#### 说明

##### 消除 Cache 中的 ReferenceConfig，将销毁 ReferenceConfig 并释放对应的资源

##### 缺省 ReferenceConfigCache 把相同服务 Group、接口、版本的 ReferenceConfig 认为是相同，缓存一份。即以服务 Group、接口、版本为缓存的 Key

### 线程栈自动dump

#### 应用场景

##### 当业务线程池满时，我们需要知道线程都在等待哪些资源、条件，以找到系统的瓶颈点或异常点。dubbo通过Jstack自动导出线程堆栈来保留现场，方便排查问题

#### 默认策略

##### 导出路径，user.home标识的用户主目录
导出间隔，最短间隔允许每隔10分钟导出一次

#### 指定导出路径

##### # dubbo.properties
dubbo.application.dump.directory=/tmp

##### <dubbo:application ...>    <dubbo:parameter key="dump.directory" value="/tmp" /></dubbo:application>

### Java序列化（Kryo和FST）

#### 启用Kryo和FST

##### <dubbo:protocol name="dubbo" serialization="kryo"/>

##### <dubbo:protocol name="dubbo" serialization="fst"/>

## API配置参考手册

## schema配置参考手册

## 协议参考手册

## 注册中心参考手册

## telnet命令参考手册

## 在线运维命令-QOS

## maven插件参考手册

## 服务化最佳实践

## 推荐用法

## 容量规划

## 性能测试报告

## 测试覆盖率报告
