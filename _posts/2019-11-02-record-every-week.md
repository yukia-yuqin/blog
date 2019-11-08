---
layout: post
title: 每周学到的一点小东西
tags: week
---

record for myself. since 2019-03-26.<br>
### 2019 week45
- 多线程通信方式？被问到过好多次这个问题，仍然不知道最好的答案。
- 进程和线程的区别？同样被问到好多次这个问题，仍然不知道最好的答案。
- .bashrc文件与.bash_profile文件的区别
   - login shell会读取的文件有：/etc/profile、$HOME/.bash_profile,$HOME/.bash_login，$HOME/.profile，按以上顺序读取。
   - no login shell 在打开的时候，执行的文件是：$HOME/.bashrc，而.bashrc又会执行/etc/bashrc文件。
   - 在.bash_profile文件中加载.bashrc文件，重新登录终端的时候，就不需要再手动source了。


### 2019 week44
- youtube李永乐
   - 电磁波 f=2.45GHZ; 水蛋白质脂肪震动摩擦生热；微波无害：γ射线，x射线（频率越高才能致癌，使DNA分子断链），光，微波，中波，长波；金属屏蔽，金属反射电磁波；注意:不能放金属，不能放封闭物品（鸡蛋），不能放普通塑料(产生有害物质) 
- 使用豆瓣记录自己的看书看电影的历程！良心软件！
- 学习是个漫长的过程，要相信每天进步一点点，就会有变化，积少成多，不学习是一定不会进步的！什么不懂就要学什么。不要担心学的东西没有用！
- 最近为了m家的rsde面试，用了一周的时间看了leetcode上的460道题目，主要从youtube的花花酱那里学习，excellent！
- 最近几个月找工作，没怎么记录。

### 2019 week30
- C++rand() https://stackoverflow.com/questions/9878965/rand-between-0-and-1
- 电磁炉和 微波炉加热原理
   - 电磁炉是采用磁场感应涡流加热原理， 他利用电流通过线圈产生磁场，当磁场内之磁力通过含铁质锅底部时， 即会产生无数之小涡流，使锅体本身自行高速发热，然后再加热于锅内食物。
   - 微波炉的心脏是磁控管。这个叫磁控管的电子管是个微波发生器，它能产生每秒钟振动频率为24.5亿次的微波。这种肉眼看不见的微波，能穿透食物达5cm深，并使食物中的水分子也随之运动，剧烈的运动产生了大量的热能，于是食物煮熟了。这就是微波炉加热的原理。用普通炉灶煮食物时，热量总是从食物外部逐渐进入食物内部的。而用微波炉烹饪，热量则是直接深入食物内部，所以烹饪速度比其它炉灶快4至10倍，热效率高达80%。

### 2019 week 29
- 阅读专业书籍后如何转化成自己的知识，如何高效做读书笔记？有时候去面试碰上一个问题一个知识点明明是看过的，但是自己就是说不上来。
   -  谢谢小姐姐非常有必要的习惯，预计时间是正常阅读时间的1.5倍，前两个小时看30面，把不会的理解有误的勾下来，最后一个小时记笔记，有逻辑性，小节标题做辅助。每章一条笔记。C+primer 10 多条 面试之前全部看一遍。
- 如何平衡知识广度和深度问题，比如说体系结构和计算机算法以及工程性问题。	并不是一个tradeoff的关系。能有多广有多广，能有多深有多深。
- 早晨7点半起床，8点出门，9-17:30点自己学习，看书+公开课，晚上自己的时间，锻炼+coding。
- Leetcode周赛 
- code : code forces 晚上做比赛 白天清掉 半年，（废）
- 读编程类经典书籍，比如《java核心技术卷一》重点是复现书上的代码示例还是把书上的重点文字用笔记记录下来？目的是理解记忆然后之后使用:-D？
   - 理解高层次的思想，用文字记录下来，常归纳总结，有新的体会啊。复现代码用处并不大。
- 一句话总结自己：一个实习经验丰富有Paper的coder.
-  外企招聘特点 
   -   职位：general hire（software developer） 2. 考察：算法为主 3. 流程：官申/内推->OA->电面->onsite->AA->offer 4. 时间：晚、慢（面试9月->offer11月）
8成以上题目是算法题。内推。Hiho coder 微软。9月BAT 的offer 拿满。
-  针对5家企业的时间线，链接。模拟题。快速，准确。
   - Airbnb 8月初 官网申请 8月底 hr电话沟通 9月中 [3轮现场技术面](http://poj.org/problem?id=2739 http://poj.org/problem?id=2823 http://poj.org/problem?id=3050) 10月初 2轮远程文化面 10月中 口头offer 10月底 offer
   - 技术面非常难，现场运行代码。文化面：我是好人，我热爱旅游，热爱世界和平。
   - Amazon 8月中 官网申请 8月中 [在线笔试](https://leetcode.com/contest/leetcode-weekly-contest-46) 8月中 [2轮现场技术面](https://leetcode.com/problems/trim-a-binary-search-tree https://leetcode.com/problems/implement-magic-dictionary) 8月底 口头offer 9月底 offer 中国：购物，本地化，Kindle。题目相对简单。
   - Google 3月初 申请实习生 3月中 [实习电面](http://poj.org/problem?id=2115) 4月初 实习onsite （http://poj.org/problem?id=3669） 4月底 实习offer 9月中 2轮转正技术面 （http://poj.org/problem?id=3614 https://leetcode.com/problems/design-tinyurl） 11月初 通过hiring committee 11月中 team match 12月底 offer 实习好进！正式：4轮算法面试。
   - Hulu 8月初 内推 9月中 技术电面 （http://poj.org/problem?id=3258 http://poj.org/problem?id=2229） 9月底 3轮技术onsite （http://poj.org/problem?id=2236 http://poj.org/problem?id=1862） 10月中 总监终面 11月中 offer 技术氛围特别好。常年招聘实习生。面试难度大。
   - Microsoft 3月底 在线笔试 （http://hihocoder.com/contests/past） 4月中 3轮实习技术面 （http://poj.org/problem?id=3009 http://poj.org/problem?id=1258） 5月中 实习offer 8月底 夏令营2轮技术面 9月初 转申美国岗 10月底 4轮技术面 11月初 offer 最难的是在线笔试。特别看重CS 基本功，10面，2面算法，8面 potential，开放思维，联想到缓存，调度问题，面向对象程序设计，操作系统，线程进程特别深。

### 2019 week 28
- 复杂度
   - 	一秒CPU差不多能进行八次方的运算，通过时间复杂度估算，超九次方肯定不过，七次方及以内一般比较轻松，但有时还要看你常数的
- 1e1+7 = 17 e1为10的1次方  1e9+7 = 1,000,000,007 

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