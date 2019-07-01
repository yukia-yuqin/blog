---
layout: post
title: 机器学习面试
tags: interview
categories: interview
---
记录一下网上扒下来的以及自己的面试经历。<br>

### 技术面问题
- fast rcnn
- adaboost 
- gbdt 
- XGBOOST 
   - xgboost，在求解速度，对异常值处理上要比gbdt要快
- random forest
- lgb
- 神经网络embedding层和w2v中的embedding的实现区别
- L1、L2的区别，L1为什么可以保证稀疏？
- 深度学习的优化方法有哪些？ sgd、adam、adgrad区别？ adagrad详细说一下？为什么adagrad适合处理稀疏梯度？ 
- DL常用的激活函数有哪些？ 
- relu和sigmoid有什么区别，优点有哪些？ 
- 什么是梯度消失，标准的定义是什么？ 
- DNN的初始化方法有哪些？ 为什么要做初始化？ kaiming初始化方法的过程是怎样的？ 
- xgboost里面的lambdarank的损失函数是什么？ 
- xgboost在什么地方做的剪枝，怎么做的？ 
- xgboost如何分布式？特征分布式和数据分布式？ 各有什么存在的问题？ 
- lightgbm和xgboost有什么区别？他们的loss一样么？ 算法层面有什么区别？ 
- lightgbm有哪些实现，各有什么区别？
- EM
- LDA
- 要懂得算法的推导、适用场景、使用的Trick、分布式实现
- CNN、RNN、LSTM的基本原理，不同激活函数的差异等等，如果是面的传统机器学习岗的话，DL问的不深，但一定会问。
- [softmax][softmax]
- [逻辑斯蒂回归][逻辑斯蒂回归]
- 贝叶斯法则
- MLE 的假设（在机器学习判别模型中，假设所有的x都是均匀的，算极大似然的时候p(x,y)=P(x)p(y|x)，所以可以直接算P(y|x)。？（兰艳艳说的，对吗?））
- [机器学习面试题总结][机器学习面试题总结]


### 深度学习
- [bottleneck1][bottleneck1]  [bottleneck2][bottleneck2] 
- [Mobilenetv2][mobileNetV2]
- BP [BP1]

### 无监督学习
- 无监督学习的优势
   - Raw data cheap. Labeled data expensive.
   - Save memory/computation.
   - Reduce noise in high-dimensional data.
   - Useful in exploratory data analysis.
   - Often a pre-processing step for supervised learning.
- 技术
   - [自编码机(Autoencoding)][自编码机(Autoencoding)]
   - [随机森林(Random forests)][随机森林(Random forests)]
   - [主成分分析(PCA)][主成分分析(PCA)]
   - [随机森林(Random forests)][随机森林(Random forests)]
   - GAN
- 聚类的类型
   - 分层聚类 & 划分聚类
- GMM VS K-Means
   - K-means
      - Loss function: minimize sum of squared distance. 
      - Hard assignment of points to clusters. 
      - Assumes spherical clusters with equal probability of a cluster. 
   - GMM
      - Minimize negative log likelihood. 
      - Soft assignment of points to clusters. 
      - Can be used for non-spherical clusters with different probabilities. 
- 分层聚类中各种类间距离度量的优劣
   - MIN  Advantage: Non-spherical, non-convex clusters Problem: Chaining
   - MAX  Advantage: more robust against noise (no chaining) Problem: Tends to break large clusters,
- DBSCAN
   - Advantages （Not need to specify the number of clusters / Arbitrary shape cluster / Robust to outliers ）
   - Disadvantages （Difficult parameter selection (MinPts,E) /Not proper for data sets with large differences in densities ）
- 特征选择和特征提取
   -  什么是维度爆炸 （当数据的维度非常大的时候，点与点之间的距离和密度将会变得非常没有意义，最近距离几乎等于最远距离，意味着所有点之间的距离几乎相等。）
   - 什么是维度约减 （将高维数据映射到低维空间 基本想法：数据本质上的维度就是比较小的，或者与学习相关的维度是小的）
   - PCA的优点和缺点 （Eigenvector method / No tuning parameters / Non-iterative / No local optima || Limited to second order statistics / Limited to linear projections）
   - NMF（非负矩阵分解）
   - 非线性的特征提取（）
      - **Metric MDS** and **Isomap** compute embeddings that seek to preserve interpoint straight-line (Euclidean) distances or geodesic distances between all pairs of points. Hence they are global methods. 
      - Both **locally linear embedding (LLE)** and **Laplacian eigenmap** try to recover the global nonlinear structure from local geometric properties. They are local methods. 
      - Overlapping local neighborhoods, collectively analyzed, can provide information about the global geometry. 
   - 小结 （Dimension Reduction: mapping of the original high-dim data into a lower-dim space）
      - Main idea: Minimization of reconstruction error / Maximization of variance。 
      - Algorithms: Linear (PCA, NME, RP) /  Non-linear (KPCA, LLE, LE) 
      - Beyond: Robust, probabilistic, sparse ... 
      - 主成分分析（Principal Component Analysis,PCA)、线性判别分析（Linear Discriminant Analysis,LDA）、等距映射（Isomap）、局部线性嵌入（Locally Linear Embedding,LLE）、Laplacian 特征映射（Laplacian Eigenmaps）、局部保留投影（Local Preserving Projection,LPP）、局部切空间排列（Local Tangent Space Alignment,LTSA）、最大方差展开（ Maximum Variance Unfolding,MVU）
      - 线性降维方法主要包括PCA、LDA、LPP（LPP其实是Laplacian Eigenmaps的线性表示）；非线性降维一类是基于核的，如KPCA，此处暂不讨论；另一类就是通常所说的流形学习：从高维采样数据中恢复出低维流形结构（假设数据是均匀采样于一个高维欧式空间中的低维流形），即找到高维空间中的低维流形，并求出相应的嵌入映射。非线性流形学习方法有：Isomap、LLE、Laplacian Eigenmaps、LTSA、MVU整体来说，线性方法计算块，复杂度低，但对复杂的数据降维效果较差。
      - 监督式和非监督式学习的主要区别在于数据样本是否存在类别信息。非监督降维方法的目标是在降维时使得信息的损失最小，如PCA、LPP、Isomap、LLE、Laplacian Eigenmaps、LTSA、MVU；监督式降维方法的目标是最大化类别间的辨别信，如LDA。事实上，对于非监督式降维算法，都有相应的监督式或半监督式方法的研究。
      - [全局方法不仅考虑样本几何的局部信息，和考虑样本集合的全局信息，及样本点与非临近点之间的关系。全局算法有PCA、LDA、Isomap、MVU。][降维方法]

### 人工智能
- “智能”本身就没有明确的定义
- 计算机领域的人工智能指对“智能代理“的研究，可以是硬件、软件，可以感知环境、采取行动以能达到其特定目标的任何设备都是智能代理。
- 为什么下围棋进展如此快？
   - 因为下围棋可以由机器自己判定输赢，因此可以大量的模拟，增强学习。但像语音识别和人脸识别等是不能由机器自己判定的，需要人来判定，因此不能采用增强学习。增强学习不能在感知类问题上使用。
- 人工智能为什么火了起来？
   - A+B+C 算法 大数据 计算力
- Haar like 特征在特征提取中人工选用的是1 1 -1 -1 矩阵可以表示两个部分的图像相减，而在CNN中，这个1 1 -1 -1 是学习得到的。
- 人工智能以后？小样本学习方法？
![AI][AI]
- 相关
   - 奇点临近/人工智能时代/Our Final Invention 终极发明/超级智能/终极算法 The Master Algorithm
   - Her/人工智能/我，机器人/鹰眼/超能陆战队/机械姬
   - 新智元/机器之心/36氪

### 数据挖掘
- [数据挖掘十大算法][数据挖掘十大算法]
- [KNN][KNN]
   - 
### 其他
- [MLE LSE MAP之间的关系][MLE LSE MAP之间的关系]
- [距离度量方法][距离度量方法]
   
### 链接<br>
[随机森林(Random forests)]:https://en.wikipedia.org/wiki/Random_forest
[K均值聚类(K-means clustering)]:https://www.youtube.com/watch?v=RD0nNK51Fp8
[主成分分析(PCA)]:https://www.quora.com/What-is-an-intuitive-explanation-for-PCA
[自编码机(Autoencoding)]:http://ufldl.stanford.edu/tutorial/unsupervised/Autoencoders/
[BP1]:http://neuralnetworksanddeeplearning.com/chap2.html
[逻辑斯蒂回归]:http://blog.csdn.net/bitcarmanlee/article/details/51165444
[softmax]:http://deeplearning.stanford.edu/wiki/index.php/Softmax%E5%9B%9E%E5%BD%92
[AI]:{{"/AIdevelop.png" | prepend: site.imgrepo }}
[bottleneck1]:https://blog.csdn.net/u011974639/article/details/76737547
[bottleneck2]:https://blog.csdn.net/u013709270/article/details/78838875
[mobileNetV2]:https://www.zhihu.com/question/38102762
[降维方法]:http://blog.csdn.net/xiaowei_cqu/article/details/7522368
[机器学习面试题总结]:https://zhuanlan.zhihu.com/c_129612503
[数据挖掘十大算法]:https://zhuanlan.zhihu.com/p/56078018
[MLE LSE MAP之间的关系]:https://www.zhihu.com/question/20447622
[KNN]:https://www.cnblogs.com/lesleysbw/p/6074662.html
[KNN1]:https://blog.csdn.net/pipisorry/article/details/53156836
[距离度量方法]:http://sklearn.apachecn.org/cn/latest/modules/generated/sklearn.neighbors.DistanceMetric.html#sklearn.neighbors.DistanceMetric