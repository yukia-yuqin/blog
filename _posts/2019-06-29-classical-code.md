---
layout: post
title: 经典代码
tags: interview common
categories: interview
---
记录一下网上扒下来的以及自己的面试经历。<br>

### C#
- 写byte[]数组到文件中
```C# 
byte[] amr = File.ReadAllBytes(@"123.amr");
var astring = String.Join(",", amr);
File.WriteAllText(@"222.txt", astring);
```
- 循环
```C# 
foreach (string s in pinyinSeq ){}
```
- 拆分字符串
```C#
string[] pinyinSeq = pinyinStr.Split(_content_sep, StringSplitOptions.RemoveEmptyEntries);
```

### C++
- C++ 分割字符串 变为stringstream
```C++
stringstream ss(path);
	while(getline(ss,tmp,'/')) {
		if (tmp == "" or tmp == ".") continue;
```
### python
- 随机分隔
```python
from numpy.random import RandomState
rand_state = RandomState(0)
rand_state.shuffle(ratings)
可以重复实现在0随机数下的结果
train_pct = 0.9
rand_state = RandomState(0)
rand_state.shuffle(ratings)
train_size = int(train_pct * ratings.shape[0])
train = ratings[:train_size]
validation = ratings[train_size:]
```