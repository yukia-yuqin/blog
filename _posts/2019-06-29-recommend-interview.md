---
layout: post
title: 推荐算法面试
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

### 技术面问题
#### 关于简历内容部分
- FM的公式，求导
- 特征选择的方法 filter, wrapper, bedding 选择
- word2vec, CBOW 和 Skip-gram 模型,两种模型的适用场景, Negative Sampling, Hierarchical Softmax
   * [skipgram在大数据集上效果好][word2vec] 
#### 其他基础部分
- SVM原理
- SVM与MF的区别 (第一个角度是是否需要满足矩阵是全填充的，另一个角度从计算复杂度上进行介绍的)
- 说一下LR (从线性回归入手过渡到逻辑回归，他们是对于特征的线性组合，并且假设数据是线性可分的，同时可以通过超平面将之分离，另外介绍了可以通过最大似然来推导出LR)
- 树模型是否需要归一化 （不需要）
- 模型过拟合与欠拟合，如何解决 （）
- 偏差与方差
- 了解最近MF与深度学习结合的东西吗 (何向南的神经协同过滤)
- hmm
- fast rcnn
- 要看《统计学习方法》
- 介绍K-means算法，并给出找起始点的策略


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