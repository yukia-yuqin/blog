---
layout: post
title: 智力
tags: interview
categories: interview
---

IQ 感人 TOT<br>
<br>

### 别人遇到的
- 100个囚犯从前往后坐成一列。坐在最后面的那个囚犯能够看到其余99个囚犯，坐在最前面的 那个囚犯啥也看不见。看守给每个囚犯戴上一顶黑色的或者白色的帽子。然后，看守会从后往前依 次叫这些囚犯猜测自己头顶上的帽子的颜色。如果哪个囚犯猜对了，他就自由了。坐在前面的每一 个囚犯都可以听到后面的囚犯的猜测。如果这100个囚犯事先可以商量好一种策略，那么最理想的策 略是什么？
   - 他可以数一数他前面99个人一共有多少顶白帽子，并约定他猜“黑”表示他前面共有偶数顶白帽，他猜“白”表示他前面共有奇数顶白帽。


- 简历面
   - 实习一
      - 微服务做过哪些？
         - 微服务架构是一项在云中部署应用和服务的新技术。 
      - 了解spring cloud吗？
         - Spring Cloud有一套丰富且集成良好的JAVA库，作为应用栈的一部分解决所有运行时问题。因此，微服务本身可以通过库和运行时代理解决客户端服务发现、负载均衡、配置更新、统计跟踪等。工作模式就像单实例服务集群（译者注：集群中master节点工作，当master挂掉后，slave节点被选举顶替。）并且一批工作也是在JVM中被管理。
         - Kubernetes是多语言的，不仅仅针对Java平台，而是以通用的方式为所有语言解决分布式计算问题。Kubernetes提供了配置管理、服务发现、负载均衡、跟踪、统计、单实例、平台级和应用栈之外的调度工作。该应用不需要任何客户端逻辑的库或代理程序，可以用任何语言编写。
         - 有些需求，Spring Cloud表现更好，有需求则是Kubernetes，也有些需求，两者可以用不同的方式满足。好消息是，Spring Cloud和Kubernetes在使用上并不冲突。例如，Spring Cloud提供Maven插件来创建单独JAR应用程序包。结合Docker、Kubernetes的声明式部署和调度能力，轻松运行微服务。同样，Sring Cloud以应用程序内的包装库的形式来支持弹性伸缩，微服务容错使用Hystrix（bulkhead和断路器模式）与Ribbon（负载均衡）。但这些是不够的，当组合Kubernetes健康检查、程序重启和自动伸缩能力，微服务才真正变成一个强壮的系统。结合使用Spring Cloud和Kubernetes，用Spring Cloud提供应用程序打包，Docker和Kubernetes提供部署和调度；Spring通过Hystrix线程池提供应用程序内隔离，Kubernetes通过资源、进程和命名空间隔离；Spring为每个微服务提供健康终端，Kubernetes执行健康检查并且为健康服务的通信提供路由；Spring外部化且升级配置，Kubernetes给每个微服务分配配置……这样的例子还有很多。
      - 了解Dubbo吗？
         - Dubbo是阿里的开源分布式服务框架，一款高性能、轻量级的开源Java RPC框架，它提供了三大核心能力：面向接口的远程方法调用，智能容错和负载均衡，以及服务自动注册和发现。
         - 那RPC有哪些?
               - Remoting: 网络通信框架，实现了 sync-over-async 和 request-response 消息机制.
               - RPC: 一个远程过程调用的抽象，支持负载均衡、容灾和集群功能
               - Registry: 服务目录框架用于服务的注册和服务事件发布和订阅
      - dotnet framework 和 dotnet core的区别
         - core需要的系统内核的dll库少很多，docker的基础镜像非常小。在云环境下易于伸缩。
         - .NET Core 跨平台，NET Framework 是Windows下特有的。
         - 它们都实现NET Standard Library。
         - [.NET Core 全面扫盲贴][.NET Core 全面扫盲贴]
      - 遇到了什么困难？
         - 有一些库在core中不支持 - 重构代码
      - C++/CLI 到 C++
         - 使用 C++/CLI 调用 Native 代码时，再也不需要编写额外的 P/Invoke 代码，只需要引入头文件，然后直接调用就可以了。
         - P/Invoke的全称是Platform Invoke (平台调用) 它实际上是一种函数调用机制通 过P/Invoke我们就可以调用非托管DLL中的函数实际上很多NET基类库中定义的类 型内部部调用了从Kernel32.dll，User32.dll，gdi32.dll等非托管DLL中导出的函数。
      - C++ 了解多吗？
         - [20道必须掌握的C++面试题][20道必须掌握的C++面试题]
      - Docker
      - Kubernetes
   - 实习2
      - LR+GBDT
         - [LR+GBDT](http://xudongyang.coding.me/ctr-models/)
         - [LR+GBDT](https://blog.csdn.net/u014033218/article/details/88382259)
         - stacking思想的二分类器模型，解决二分类问题
         - GBDT算法的特点正好可以用来发掘有区分度的特征、特征组合，减少特征工程中人力成本。
         - GBDT首先对原始训练数据做训练，得到一个二分类器，当然这里也需要利用网格搜索寻找最佳参数组合。网格搜索，正如mosthated说的，Grid Search就是穷举，穷举所有的超参组合。当你对决策树调参，如果只对一个超参优化，比如树的最大深度，尝试[3, 5, 7]。如果你还想对分裂标准进行调参，分别试试gini和entropy，那么就相当要对2×3=6组参数进行尝试。事实上，在用GBDT构造新的训练数据时，采用的也正是One-hot方法。并且由于每一弱分类器有且只有一个叶子节点输出预测结果，所以在一个具有n个弱分类器、共计m个叶子结点的GBDT中，每一条训练数据都会被转换为1*m维稀疏向量，且有n个元素为1，其余m-n 个元素全为0。
         - 首先，目前我所了解到的GBDT的实现方式有两种：一是利用Scikit-learn中的ensemble.GradientBoostingClassifier ，二是利用lgb里的params={ 'boosting_type': 'gbdt' }参数。在lgb中，因为是二分类问题，所以设置 {'boosting_type': 'gbdt','objective': 'binary','metric': {'binary_logloss'}}，然后设置树的个数及每棵树的叶子结点个数{'num_leaves': 64,'num_trees': 100}
         - 为什么用GBDT 不用RF？
            - RF也是多棵树，但从效果上有实践证明不如GBDT。且GBDT前面的树，特征分裂主要体现对多数样本有区分度的特征；后面的树，主要体现的是经过前N颗树，残差仍然较大的少数样本。优先选用在整体上有区分度的特征，再选用针对少数样本有区分度的特征，思路更加合理，这应该也是用GBDT的原因。
         - 现在，我们思考这样一个问题，Logistic Regression是一个线性分类器，也就是说会忽略掉特征与特征之间的关联信息，那么是否可以采用构建新的交叉特征这一特征组合方式从而提高模型的效果？
         其次，我们已经在2.3小节中了解到GBDT很有可能构造出的新训练数据是高维的稀疏矩阵，而Logistic Regression使用高维稀疏矩阵进行训练，会直接导致计算量过大，特征权值更新缓慢的问题。
         针对上面可能出现的问题，可以翻看我之前的文章：FM算法解析及Python实现 ，使用FM算法代替LR，这样就解决了Logistic Regression的模型表达效果及高维稀疏矩阵的训练开销较大的问题。然而，这样就意味着可以高枕无忧了吗？当然不是，因为采用FM对本来已经是高维稀疏矩阵做完特征交叉后，新的特征维度会更加多，并且由于元素非0即1，新的特征数据可能也会更加稀疏，那么怎么办？
         所以，我们需要再次回到GBDT构造新训练数据这里。当GBDT构造完新的训练样本后，我们要做的是对每一个特征做与输出之间的特征重要度评估并筛选出重要程度较高的部分特征，这样，GBDT构造的高维的稀疏矩阵就会减少一部分特征，也就是说得到的稀疏矩阵不再那么高维了。之后，对这些筛选后得到的重要度较高的特征再做FM算法构造交叉项，进而引入非线性特征，继而完成最终分类器的训练数据的构造及模型的训练。
         - gbdt 输入 onehot 编码的样本的特征
         - 输出 样本在每个弱分类器的结果，假设所有的分类器共有m个叶子节点，共有n棵弱分类器，就是一个1*m维的向量，里面有n个1，其余全为0。
         - [训练目标 对数损失 = logloss = 交叉熵损失 包含 (binary loss 二分类，交叉熵损失的特例，概率不为1即为0) ](https://www.zhihu.com/question/36307214)
         - 优化方法 adam, Momentum
      - Spark
         - [Spark的WordCount的示例](https://www.zhihu.com/question/26568496)
         - 宽依赖（依赖多个分区）和窄依赖（只依赖一个分区）)
         - [Transformation：](ttps://qindongliang.iteye.com/blog/2405698) 代表的是转化操作就是我们的计算流程，返回是RDD，可以是一个链式的转化，并且是延迟触发的。 Action：代表是一个具体的行为，返回的值非RDD类型，可以一个object，或者是一个数值，也可以为Unit代表无返回值，并且action会立即触发job的执行。
         - [map 和 mapPartition的区别](https://yezhwi.github.io/bigdata/2018/05/03/Spark%E5%B8%B8%E7%94%A8%E7%AE%97%E5%AD%90%E5%AE%9E%E8%B7%B5%E6%80%BB%E7%BB%93/)



[.NET Core 全面扫盲贴](https://www.zybuluo.com/wddpct/note/442464)
[20道必须掌握的C++面试题](https://m.w3cschool.cn/cpp/cpp-a9no2ppi.html)
[LR+GBDT](http://xudongyang.coding.me/ctr-models/)

