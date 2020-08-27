---
layout: post
title: 单元测试之Mockito与PowerMock
tags: 工具
categories: 工具
---

## Mockito和PowerMock

为了解决这种问题，Mockito和PowerMock诞生了。这两种工具都可以用一个虚拟的对象来替换那些外部的、不容易构造的对象，便于我们进行单元测试。两者的不同点在于Mockito对于大多数的标准单测case都很适用，而PowerMock可以去解决一些更难的问题（比如静态方法、私有方法等）。https://www.jianshu.com/p/51930cc5dcf9 【待看 0729】

junit 4.x 5.x 

testNg 单元测试的另一个方向，没仔细讲

mock  powermock （补充Mockito，静态变量）/ easymock / mockito （好） / jmock

behavior testing / concordion （重构类型测试？测试文档？数据报表）/ cucumber （ruby最早搞的） （功能测试）

jenkins / git / github/ git workflow （集成工具）

puppet / ansible / saltstack （部署的动作 CI/CD）

docker

es 日志

grafana 

jira

confluence page (wiki)

sonar / sonar scan (checksytle, findbugs, pmd静态代码检查和分析, error)



单元测试的规范：

- 执行够快 、 自动的、 不应该依赖于其他unit test、不依赖外部资源（网络资源）、 代码应该有意义、任何时候执行任何环境执行结果一样、
- 测试替身：test doubles，dummy\stub\mock\fake\spy

> <groupId>org.apache.maven.plugins</groupId> maven的Pom.xml缺少这一句话找半天

- 学习了How to stub, stubbing void methods, stubbing method with exception, stubbing consecutive calls, stubbing with real call, stubbing with callback.

# Junit

- [  JUnit4中@Before、@After、@Test等注解的作用](https://www.cnblogs.com/flypig666/p/11505277.html)

  @Before：初始化方法  对于每一个测试方法都要执行一次（注意与BeforeClass区别，后者是对于所有方法执行一次）
  @After：释放资源  对于每一个测试方法都要执行一次（注意与AfterClass区别，后者是对于所有方法执行一次）
  @Test：测试方法，在这里可以测试期望异常和超时时间 
  @Test(expected=ArithmeticException.class)检查被测方法是否抛出ArithmeticException异常 
  @Ignore：忽略的测试方法 
  @BeforeClass：针对所有测试，只执行一次，且必须为static void 
  @AfterClass：针对所有测试，只执行一次，且必须为static void 
  一个JUnit4的单元测试用例执行顺序为： 
  @BeforeClass -> @Before -> @Test -> @After -> @AfterClass; 
  每一个测试方法的调用顺序为： 

  @Before -> @Test -> @After; 

