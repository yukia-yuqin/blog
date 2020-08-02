---
layout post
title idea快捷键+maven+git+sql语句+jetty
tags 工具
categories 工具
---

## idea快捷键

idea中窗口最大化---->Windows 上： Ctrl+Shift+F12

ctrl+shift+z恢复撤回代码

**ctrl + Alt + V (返回属性变量)**

   shift+ctrl+u (大小写的切换)

   **Ctrl+Alt+L，格式化代码**

某个类型的用法 ctrl+B

   Ctrl+D 将当前行复制到下一行

 

   Ctrl+Alt+T，可以把代码包在一个块内，例如：try/catch 也可抛错误

 

   快捷方式一（光标移到该代码行，Alt+Enter），可以异常外抛出，也可以try-catch：

 

   Ctrl+Shift+Space，自动补全代码（提示）

 

   Ctrl+O，重写方法

 

   Ctrl+I，实现方法

 

   连安两下 shift 查找文件

 

   CtrL +shift +r 全局搜索：

 

   ctrl +r 替换当前页的单词

 

   代码格式化： shfit + G(自定义) //ctrl +alt +L

 

  alt+capslk(大小写切换)+鼠标左键 或者：ALT + 鼠标左键  列编辑模式 

 

1 查看接口的实现类：Ctrl+Alt+B：

 

**2：查看一个类中有什么方法：Alt+7 或 点左侧边栏Structure**

 

2 返回上/下个光标地方Alt+Ctrl+箭头(向左) 和 Alt+ Ctrl+箭头(向右)---（全键盘）

而本机为Alt+Ctrl+Pgup和Alt+Ctrl+Down

**3： 查看Java方法调用树(被调/主调)：Ctrl+Alt+H**

 

**5 查看类继承关系图：Ctrl+Alt+U**

**6查看当前类的继承树：Ctrl+H**

 

**7 查看定义的变量在哪里被调用：Ctrl+Alt+F7**

**查看一个类中有什么方法：Alt+7 或 点左侧边栏Structure**

 

 **列编辑alt +左键**



## maven

maven 命令的格式为 mvn [plugin-name][goal-name]，可以接受的参数如下。

##### Maven packaging打包类型

- Maven项目的常用的打包类型分为：pom、jar、war等类型

- pom文件除了GAV(groupId, artifactId, version)是必须要配置的，另一个重要的属性就是packaging打包类型，所有的父级项目的packaging都为pom，packaging默认是jar类型，如果不作配置，maven会将该项目打成jar包。作为父级项目，还有一个重要的属性，那就是modules，通过modules标签将项目的所有子项目引用进来，在build父级项目时，会根据子模块的相互依赖关系整理一个build顺序，然后依次build。

- 对于各个子项目，需要在其对应的pom文件开头申明对父级项目的引用，通过GAV实现。对于子项目自己的GAV配置，GV如果不配置，则会从父级项目的配置继承过来。子模块可通过dependencies标签来添加自己的依赖，此外子类项目的packaging值只能是war或者jar，前面已经说过，packaging默认是jar类型。如果是需要部署的项目，则需要打包成war类型，如果只是内部调用或者是作服务使用，则推荐打包成jar类型。

- 项目的打包类型：pom、jar、war

  packing默认是jar类型，

  <packaging>pom</packaging>  -->  父类型都为pom类型

  <packaging>jar</packaging>   -->  内部调用或者是作服务使用

  <packaging>war</packaging>  -->  需要部署的项目

- dependencies  项目相关依赖配置，如果在父项目写的依赖，会被子项目引用，一般父项目会将子项目公用的依赖引入（将在之后详细讲解。

  ```
  <dependencies>
      <dependency>
              <groupId>junit</groupId>
              <artifactId>junit</artifactId>
              <version>4.12</version>
      </dependency>
  </dependencies  
  ```
  
- groupId：父项目的构件标识符  artifactId：父项目的唯一标识符

- prerequisite 项目构建的前提

## git



## sql语句

## jetty

参考《深入分析Java Web技术内幕》 单纯比较Tomcat和Jetty的性能意义不是很大，只能说在某些使用场景下它们的表现各有差异，因为它们面向的使用场景不尽相同。从架构上来看Tomcat在处理少数非常繁忙的连接上更有优势，也就是连接的生命周期如果比较短，Tomcat的性能比较优。而Jetty则恰好相反，**Jetty可以同时处理大量链接并且长时间的保持这些链接**，例如，**一些Web聊天应用非常适合用Jetty服务器**，淘宝的Web 旺旺就是用Jetty作为Servlet引擎。《深入分析Java Web技术内幕》

jetty主要目标是做为其他程序的嵌入式web服务器组件，低耦合，可插拔，特点是短小精悍，极易嵌入，比如作为某些大型程序的web api接口，jetty的人生理想是做一颗又红又专的螺丝钉，至少到目前为止jetty还没有想过自立门户或者鸠占鹊巢。

tomcat对标的是apache，iis，是Java届与上述两位兄弟一摸一样的人生目标，一摸一样的人生五大三粗，一摸一样的亮点槽点，大而全，差不多先生，这三位是历史上web的三驾马车.

后来一个德意志小伙搞了一个lighttpd，不过由于疏于维护，虽一战成名然后并卵；再后来战斗民族的小伙因为不堪忍受apache，亲手撸了一个nginx，社区开源搞得好，如今一骑绝尘风华正茂；

而java界也有resin这样的对手，比如网易就在使用，而jetty由于历史后发居上，设计方面和代码质量都要比老前辈tomcat好太多，当然这是优势也是弱势，通用型方面jetty就不敌tomcat了.在**云盛行的时代，jetty是香饽饽**，而tomcat越看越像老太太了，好汉只能提当年勇了。

## 黑话

冒烟测试可以理解为该种测试耗时短，仅用一袋烟功夫足够了。它的作用就是保证系统的主流程和新模块的基本功能能用，保证希望集成测试能正常开展，优点是节省测试时间，防止build 失败。缺点是覆盖率还是比较低。测试经理会和项目经理等相关人员从测试用例库中选定重要的测试用例，标记为冒烟测试用例。由此可以看到冒烟测试失败的话，会导致测试进度延期，成本和进度风险很大，因此冒烟测试失败是一个很大的项目失误，所以一般的，在发布前，开发人员会内部执行一次冒烟测试，来保证提交的版本的质量。总结：从八二法则看冒烟测试，往往冒烟测试集合了项目中最重要的功能和模块，一旦出错，系统就陷于不能使用的境地，其严重性不言而喻，而提高每次测试版本的质量，也是成本控制的一种方式，将测试前移，从源头做起，节省成本，提高产品质量的出路。

## java

- **<? extends T> 和 <? super T>** 是Java泛型中的“通配符（Wildcards）” 和 “边界（Bounds）”的概念

 Plate<？ extends Fruit> 翻译成人话就是：**一个能放水果以及一切是水果派生类的盘子。**再直白点就是：**啥水果都能放的盘子。**这和我们人类的逻辑就比较接近了。Plate<？ extends Fruit>和Plate<Apple>最大的区别就是：**Plate<？ extends Fruit>是Plate<Fruit>以及Plate<Apple>的基类。**直接的好处就是，我们可以用“*苹果盘子*”给“*水果盘子*”赋值了。上界<? extends T>不能往里存，只能往外取

**<? extends Fruit>会使往盘子里放东西的set()方法失效。但取东西get()方法还有效。**比如下面例子里两个set()方法，插入Apple和Fruit都报错。https://www.cnblogs.com/zhaoyibing/p/9051428.html

