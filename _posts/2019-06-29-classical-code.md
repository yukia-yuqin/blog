---
layout: post
title: ���ô���
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
