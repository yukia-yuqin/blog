---
layout: post
title: 每周学到的一点小东西
tags: week
---

record for myself.<br>



### 2019 week25
- Stubs & Mocks
   - Stubs provide canned answers to calls made during the test, usually not responding at all to anything outside what's programmed in for the test. Stubs may also record information about calls, such as an email gateway stub that remembers the messages it 'sent', or maybe only how many messages it 'sent'.
   - Mocks are [...] objects pre-programmed with expectations which form a specification of the calls they are expected to receive.

### 2019 week24
- 	**Portable code** is code that is not tightly coupled to one specific platform, or which is coupled as loosely as possible to platform-specific APIs. It is "portable" in that the amount of work required to move it from one platform to another is low.
Portable code is desirable when you intend to write code meant to be used by a large audience, on a wide variety of platforms.
- [PDB file][PDB]
   -  A native C++ PDB file contains quite a bit of information:
		- Public, private, and static function addresses
		- Global variable names and addresses
		- Parameter and local variable names and offsets where to find them on the stack
		- Type data consisting of class, structure, and data definitions
		- Frame Pointer Omission (FPO) data, which is the key to native stack walking on x86
		- Source file names and their lines
   -  A .NET PDB only contains two pieces of information, the source file names and their lines and the local variable names. All the other information is already in the .NET metadata so there is no need to duplicate the same information in a PDB file.
   - 有了 PDB就可以从源码级别去debug  dll

### 2019 week22
- 棕地 绿地
   - 棕地 (brownfield) 应用程序（不是完全依据最新方法或使用最新工具构建的现有应用程序）更常见 在微服务架构中尤为如此。我交流过的大部分开发团队都觉得微服务听起来像是一个不错的主意，但他们不确定如何开始使用它们，因为他们目前使用的是大型整体式应用程序。全新的（绿地）应用程序
- DevOps（Development和Operations的组合词）
   - “软件开发人员（Dev）”和“IT运维技术人员（Ops）”之间沟通合作的文化、运动或惯例。透过自动化“软件交付”和“架构变更”的流程，来使得构建、测试、发布软件能够更加地快捷、频繁和可靠。
   - 而DevOps考虑的还不止是软件部署，它是一套针对这几个部门间沟通与协作问题的流程和方法.
   - 
- 最小可行产品（MVP）

### 2019 week21
- [XML 文件][XML]
   - 应用程序配置文件是标准的 XML 文件，XML 标记和属性是区分大小写的。它是可以按需要更改的，开发人员可以使用配置文件来更改设置，而不必重编译应用程序。配置文件的根节点是configuration。我们经常访问的是appSettings，它是由.Net预定义的配置节。
- 	雷神公司是美国的大型国防合约商，总部设在马萨诸塞州的沃尔瑟姆。雷神在世界各地的雇员有73,000名，营业额约200亿美元，其中超过90%来自国防合约。根据Defense News 2005年的数据雷神是世界第五大国防合约商。
- IBM  花费五十亿美元开发360系列大型机，采用最新的集成电路技术，奠定IBM在大型机称霸的定位。IBM为计算机产业长期的领导者，在大型／小型机和便携机（ThinkPad）方面的成就最为瞩目。其创立的个人计算机标准，至今被不断地沿用和发展。2002年12月以20.5亿美元的价格将台式机硬盘业务出售给日立。2004年12月8日其PC部门出售给联想公司，金额17.5亿美元并持有联想公司股份。收购后，联想在五年内可以使用IBM的品牌。ThinkPad和ThinkCentre品牌归联想集团所有，IBM只会对server级的计算机进行维护。借由联想收购PC部门的契机，IBM开始向管理服务公司转型。
- 善用 chrome的网页翻译功能 快捷键 书+T
- Git rebase 命令

### 2019 week20
- Redistributable 是什么
   - 这个是 VC++ 的 Runtime 库，这些DLL里面有很多VC需要的库函数，如果不安装的话，可能无法运行 VC++ 编写的程序

### 2019 week19
- OSI参考模型和TCP/IP体系结构及分层协议
  ![TCPIP][TCPIP]
- C# linq语言 

### 2019 week16
- slim 库包含很多网络可以用
- 协调世界时（英语：Coordinated Universal Time，法语：Temps Universel Coordonné，简称UTC）是最主要的世界时间标准，其以原子时秒长为基础，在时刻上尽量接近于格林尼治标准时间。
- 像是Ienumerable 这种东西，都是由 .net 框架给你写好的，不需要实现，只需要返回一个可用的可枚举类型即可   An enumerator that can be used to iterate through the collection.
- 学习 心态 慢慢来
   - 心态，即调整自己那种快速求成，立竿见影的心态，因为很多收获都不可能立竿见影，即使可以那样的收获也是表面的。
   - 就是重新定一个小而实际的目标，小而实际的目标即是那些可以比较容易达到和看到效果的目标。
- PCM 
   - Pulse-code modulation的缩写，中文译名是脉冲编码调制

### 2019 week 15
- Ctrl+shift+f 切換繁簡體2019/3/16 8:49
- Someone came up with the idea that we can use an algorithm to learn the feature representation itself, aptly called feature learning. Deep learning uses a neural network to achieve this task.
- GRU   Introduced by Cho, et al. in 2014, GRU (Gated Recurrent Unit) aims to solve the vanishing gradient problem which comes with a standard recurrent neural network. 2019/3/16 10:30
- Hadamard (element-wise) product

### 2019 week13
- 给数据打标签工具  lableme or others
- [词性标注][词性标注]
- [语法分析][语法分析]
- [研究社交网络的工具包][研究社交网络的工具包]
- [一亩三分地刷题版][三分地]
- [炼丹笔记七：卷积神经网络模型设计][炼丹笔记七]
- [邮局 村庄问题][邮局 村庄问题]
   - Q: 用数轴描述一条高速公路，有V个村庄，每一个村庄坐落在数轴的某个点上，需要选择P个村庄在其中建立邮局，要求每个村庄到最近邮局的距离和最小。
   - dp[i][j]:在前i个村庄中建立j个邮局的最小耗费
   - sum[i][j]:在第i个村庄到第j个村庄中建立1个邮局的最小耗费
   - 那么就有转移方程：dp[i][j] = min(dp[i][j],dp[k][j-1]+sum[k+1][i])  DP的边界状态即为dp[i][1] = sum[1][i]; 所要求的结果即为dp[vil_num][post_num];
- [动态规划初步·各种子序列问题][动态规划初步·各种子序列问题]

## 备注
[PDB]:https://www.wintellect.com/pdb-files-what-every-developer-must-know/
[XML]:https://blog.csdn.net/liuhhaiffeng/article/details/52584468
[TCPIP]: {{"/TCPIP.jpg" | prepend: site.imgrepo }}
[三分地]: https://www.1point3acres.com/bbs/thread-137654-1-1.html 
[炼丹笔记七]:https://zhuanlan.zhihu.com/p/57738934
[邮局 村庄问题]:http://leetcode0.blogspot.com/2014/01/blog-post.html
[动态规划初步·各种子序列问题]:https://pks-loving.blog.luogu.org/junior-dynamic-programming-dong-tai-gui-hua-chu-bu-ge-zhong-zi-xu-lie
[词性标注]:http://blog.csdn.net/fxjtoday/article/details/5841453
[语法分析]:https://nlp.stanford.edu/software/lex-parser.shtml
[研究社交网络的工具包]: http://www.looooker.com/archives/13739