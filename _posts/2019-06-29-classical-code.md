---
layout: post
title: ���ô���
tags: interview common
categories: interview
---
��¼һ�����ϰ��������Լ��Լ������Ծ�����<br>

### C#
- дbyte[]���ĵ�
```C# 
byte[] amr = File.ReadAllBytes(@"123.amr");
var astring = String.Join(",", amr);
File.WriteAllText(@"222.txt", astring);
```
- ѭ��
```C# 
foreach (string s in pinyinSeq ){}
```
- �ַ����з�
```C#
string[] pinyinSeq = pinyinStr.Split(_content_sep, StringSplitOptions.RemoveEmptyEntries);
```
