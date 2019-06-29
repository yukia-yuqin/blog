---
layout: post
title: 常用代码
tags: interview
categories: interview
---

### C#
- 写byte[]入文档
```C# 
byte[] amr = File.ReadAllBytes(@"123.amr");
var astring = String.Join(",", amr);
File.WriteAllText(@"222.txt", astring);
```
- 循环
```C# 
foreach (string s in pinyinSeq ){}
```
- 字符串切分
```C#
string[] pinyinSeq = pinyinStr.Split(_content_sep, StringSplitOptions.RemoveEmptyEntries);
```
