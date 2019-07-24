---
layout: post
title: 推荐算法总结
tags: interview
categories: interview
---
记录一下网上扒下来的以及自己的面试经历。<br>

### 能力要求
- 数据分析、数据挖掘能力
- 大数据处理技术（spark、Hadoop）
- 扎实的算法基础：机器学习与推荐算法相关的LR、SVM、GBDT、DNN
- 丰富的Python、C开发经验
- 项目经验
- 机器学习岗位的面试中通常会对一些常见的机器学习算法和思想进行提问，在平时的学习过程中可能对算法的理论，注意点，区别会有一定的认识，但是这些知识可能不系统，在回答的时候未必能在短时间内答出自己的认识，因此将机器学习中常见的原理性问题记录下来，保持对各个机器学习算法原理和特点的熟练度。

### 技术面问题
#### 关于简历内容部分
- FM的公式，求导
    - [FM1][FM1] 
    - [看到的最厉害的FM的讲解][FM的讲解]
    - 上面几种深度学习模型基本是在一个固有的DNN结构上，在输入层加东西或者在隔壁加额外层来结合FNN和PNN算法在特征组合与深度学习的结合上都给出了不少启发，但是毕竟Google出品，必属精品，无疑是使用更加广泛，当然在目前机器资源越来越好的情况下，Wide&Deep也将会有更多更加复杂的深度模型将会取尝试。同时也有经验表明，在不断上各种复杂模型的前提下，CTR预估的效果还是会不断的提升。
    - FMS系列算法被广泛应用于ctr预估类的问题中，并且可以取得不错的效果，他最大特征是可以帮助解决特征组合问题
    - 原始FM算法的运行性能最快，，在工业中被适用最广最简单，其他带上神经网络的FM算法如果想在在线系统中使用得做很多离线计算和分解，比如FFM的现在复杂度是O(kn^2)，将O(n^2）中二阶计算的项尽可能的进行离线计算，在在线的时候进组合
    - FM的二阶项部分很容易使用TensorF10w进行实现，这也意味了在实验上也很容易很其他复杂算法进行组合
- [FM实战,ICME2019 & 字节跳动][FM实战]
- DeepFM
    - 基尼不纯度(一个随机事件变成它的对立事件的概率) Gini指数越小表示集合中被选中的样本被分错的概率越小，也就是说集合的纯度越高，反之，集合越不纯。
    - 基尼指数（基尼不纯度）= 样本被选中的概率 * 样本被分错的概率
- [Xgboost][Xgboost]
- 特征选择的方法 filter, wrapper, bedding 选择
- word2vec, CBOW 和 Skip-gram 模型,两种模型的适用场景, Negative Sampling, Hierarchical Softmax
   * [skipgram在大数据集上效果好][word2vec] 
- [DeepFM][DeepFM1]
    - 深度学习本身的好处：理论上可以拟合任何函数，表征能力很强；无需特征工程（传统的用特征交叉）；处理非结构数据非常好；准确的学到Item和user的非线性表示（矩阵分解是线性的）。
    - 借助FNN的思想，利用FM进行embedding，之后的wide和deep模型共享embedding之后的结果。DNN的输入完全和FNN相同（这里不用预训练，直接把embedding层看作一层的NN），而通过一定方式组合后，模型在wide上完全模拟出了FM的效果（至于为什么，论文中没有详细推导，本文会稍后给出推导过程），最后将DNN和FM的结果组合后激活输出。
    - [针对交叉（高阶）特征学习提出的DeepFM是一个end-to-end模型][DeepFM2]
    - [DeepFM在训练过程中不需要特征工程][DeepFM3] DeepFM的结构中包含了因子分解机部分以及深度神经网络部分，分别负责低阶特征的提取和高阶特征的提取。
- 推荐系统的算法中最近邻和矩阵分解各自适用场景
- 用户流失率预测怎么做（游戏公司的数据挖掘都喜欢问这个）
- 一个游戏的设计过程中该收集什么数据
- 如何从登陆日志中挖掘尽可能多的信息
- 讲一下你觉得你突出的地方，有亮点的地方。 
- LR为什么用sigmoid函数。这个函数有什么优点和缺点？为什么不用其他函数？ 
- SVM原问题和对偶问题关系？ 
- KKT条件用哪些，完整描述 
- 有一堆已经分好的词，如何去发现新的词？ 
  面试官给的提示：用这个词和左右词的关系。互信息 新词的左右比较丰富，有的老词的左右也比较丰富。还要区分出新词和老词。
- L1正则为什么可以把系数压缩成0，坐标下降法的具体实现细节 
- spark原理 
- spark Executor memory 给16G  executor core 给2个。问每个core分配多少内存 
- 对于机器学习你都学了哪些？讲一个印象深的 
  说了SVM原理，拉格朗日法，对偶问题，以及好处。 
- SVM怎么防止过拟合 
- 说了SVM里面的松弛变量。不知道对不对 
- 我主动出击，有另一大类算法决策树，说不管是LR还是SVM都不能直观的感受到决策依据。而决策树易于理解，能够直观的感受到决策依据。 
- 说了划分依据：信息增益（说了信息熵的来源，等概率时熵最大）、信息增益率、基尼系数。 
- 说了划分方法（基于信息增益的） 
- 说了C4.5比较ID3的优点。 
- 决策树如何防止过拟合 
  - 剪枝，前剪枝和后剪枝。说了REP剪枝。C4.5是悲观剪枝 
- SVM 的推导，特性？多分类怎么处理？
- LR 的推导，特性？
- SVM、LR、决策树的对比？
- GBDT 和 决策森林 的区别？
- 如何判断函数凸或非凸？
- 解释对偶的概念。
- 如何进行特征选择？
- 为什么会产生过拟合，有哪些方法可以预防或克服过拟合？
- 介绍卷积神经网络，和 DBN 有什么区别？
- 采用 EM 算法求解的模型有哪些，为什么不用牛顿法或梯度下降法？
- 用 EM 算法推导解释 Kmeans。
- 用过哪些聚类算法，解释密度聚类算法。
- 聚类算法中的距离度量有哪些？
- 如何进行实体识别？
- 解释贝叶斯公式和朴素贝叶斯分类。
- 写一个 Hadoop 版本的 wordcount。
- pagerank
- 统计机器学习（LR NB SVM）




#### 其他基础部分
- [SVM原理][svm]
- SVM与MF的区别 (第一个角度是是否需要满足矩阵是全填充的，另一个角度从计算复杂度上进行介绍的)
- [SVM的推导，特性，多分类怎么处理？][会长ZZZ]
- [LR 的推导，特性？][会长ZZZ]
- [决策树的特性？][会长ZZZ]
- [SVM、LR、决策树的对比？][会长ZZZ]
- [GBDT 和随机森林的区别？][会长ZZZ]
- [如何判断函数凸或非凸？什么是凸优化？][会长ZZZ]
- [ 如何解决类别不平衡问题？][会长ZZZ]
- [解释对偶的概念。][会长ZZZ]
- [如何进行特征选择][会长ZZZ]
- [树模型是否需要归一化 （不需要）][会长ZZZ]
- [模型过拟合与欠拟合，如何解决/ 为什么会产生过拟合，有哪些方法可以预防或克服过拟合？][会长ZZZ]
- [偏差与方差][会长ZZZ]
- [ 神经网络的原理，如何进行训练？  ][会长ZZZ]
- [介绍卷积神经网络，和 DBN 有什么区别？][会长ZZZ]
- [ 采用 EM 算法求解的模型有哪些，为什么不用牛顿法或梯度下降法？][会长ZZZ]
- [EM](https://blog.csdn.net/zouxy09/article/details/8537620)
    - EM算法就是这样，假设我们想估计知道A和B两个参数，在开始状态下二者都是未知的，但如果知道了A的信息就可以得到B的信息，反过来知道了B也就得到了A。可以考虑首先赋予A某种初值，以此得到B的估计值，然后从B的当前值出发，重新估计A的取值，这个过程一直持续到收敛为止。
    -  期望最大算法是一种从不完全数据或有数据丢失的数据集（存在隐含变量）中求解概率模型参数的最大似然估计方法。（数据丢失是指男女不知道的情况）
- [用 EM 算法推导解释 Kmeans。][会长ZZZ]
    - [EM解释Kmeans](https://www.cnblogs.com/jerrylead/archive/2011/04/06/2006910.html)
- [用过哪些聚类算法，解释密度聚类算法。][会长ZZZ]
- [常见的机器学习&数据挖掘知识点][一只鸟的天空]
- [XGBDT][XGBDT]
- 了解最近MF与深度学习结合的东西吗 (何向南的神经协同过滤)
- hmm
- fast rcnn
- 要看《统计学习方法》
- 介绍K-means算法，并给出找起始点的策略
- [霍夫丁不等式(结论:训练误差小的模型泛化误差也会小)][霍夫丁不等式]
- [斯坦福大学机器学习课程个人笔记][斯坦福大学机器学习课程个人笔记]
- 为什么KNN中要对数据进行归一化
    -	提高精度。 	防止出现值域过大的特征影响
- [归一化能不能提高梯度下降法求解最优解的速度？][归一化能不能提高梯度下降法求解最优解的速度？]
- 什么是泛化误差？
- 泊松分布
    - 泊松分布适合于描述单位时间（或空间）内随机事件发生的次数。如某一服务设施在一定时间内到达的人数，电话交换机接到呼叫的次数，汽车站台的候客人数，机器出现的故障数，自然灾害发生的次数，一块产品上的缺陷数，显微镜下单位分区内的细菌分布数等等。
- 	正确分类与训练集不同的新样本的能⼒叫做泛化（generalization）
- 为什么最大化似然的时候需要取对数
    - 将乘法变为加法//不对，还是需要对小数取一个Log.
    - 避免大量小概率的乘积会下溢

#### 结合实际场景部分
- 协同过滤(基于物品和基于用户)原理，ItermCF,UserCF,SVD矩阵分解 
- 实际场景的解决方案
- 设计一套推荐系统<br>
    推荐＝人＋场景＋物 其中，<br>
- 现在给你一个spotify，请给我设计一个音乐推荐系统
    * 首先需要历史数据 user behavior-like/dislike/comment/share/skip, dimention table,(user,item)
        - content based (不依赖用户的行为，对冷启动有用)
        - item based 
        - user based  协同体现计算相似度的时候是在用户对item的行为
        - rule based model (难易程度1, make sense程度5) 
        - `转化成classification/regression 模型 (难易程度2, make sense程度5)`
            - 要注意unbalanced data的危害以及一种random sample negative case的逻辑
        - matrix factorization (难易程度3, make sense程度2)
        - facorization machine (难易程度3, make sense程度3)
        - wide and deep learning (难易程度4, make sense程度4)
- 看一看kaggle上的tricks
- Evaluation
    - precision 推荐的准不准 recall 推荐的全不全
- 垃圾邮件过滤系统

## 前人经验
- 评语：我们要求算法工程师不仅对于机器学习算法需要了如指掌，我们更需要将算法部署到真实环境中，因此不是简单的用python训练个模型就好了，还需要将之部署到服务器上，我们更加注重计算机基础相关的东西，同学你还得加强基础训练啊。

[word2vec]:http://www.shuang0420.com/2016/06/21/%E8%AF%8D%E5%90%91%E9%87%8F%E6%80%BB%E7%BB%93%E7%AC%94%E8%AE%B0%EF%BC%88%E7%AE%80%E6%B4%81%E7%89%88%EF%BC%89/
[svm]:https://cloud.tencent.com/developer/article/1109404
[会长ZZZ]:https://www.cnblogs.com/zuochongyan/p/5407053.html
[一只鸟的天空]:https://blog.csdn.net/heyongluoyao8/article/details/47840255
[霍夫丁不等式]:https://blog.csdn.net/z_x_1996/article/details/73564926
[斯坦福大学机器学习课程个人笔记]:https://www.academia.edu/30905795/%E6%96%AF%E5%9D%A6%E7%A6%8F%E5%A4%A7%E5%AD%A6%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E8%AF%BE%E7%A8%8B%E4%B8%AA%E4%BA%BA%E7%AC%94%E8%AE%B0
[归一化能不能提高梯度下降法求解最优解的速度？]:https://blog.csdn.net/weixin_38111819/article/details/79729444
[FM实战]:https://github.com/JiDong-CS/icme2019-bytedance-grand-challenge
[Xgboost]:https://www.jianshu.com/p/7467e616f227
[DeepFM1]:https://blog.csdn.net/zynash2/article/details/79348540
[DeepFM2]:https://www.cnblogs.com/akanecode/p/8093742.html
[DeepFM3]:https://blog.csdn.net/u010159842/article/details/78789711
[FM1]:http://ju.outofmemory.cn/entry/347921
[XGBDT]:https://blog.csdn.net/yangxudong/article/details/53872141
[FM的讲解]:https://zhuanlan.zhihu.com/p/37963267