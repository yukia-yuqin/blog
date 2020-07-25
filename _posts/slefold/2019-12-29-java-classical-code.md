---
layout: post
title: Java经典代码
tags: code
categories: code
---
since 2019-6-29
经典流传<br>
<br>

### java
```java
    public static void createDefinitionSortTreeMap() {
        TreeMap<String, String> map = new TreeMap<String, String>(new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                    return o2.compareTo(o1);
            }
        });
    }
    public static void print(Map<String, String> map) {
        Iterator<Entry<String, String>> it = map.entrySet().iterator();
        while(it.hasNext()) {
            Entry<String, String> entry = it.next();
            System.out.println(entry.getKey() + " : " + entry.getValue());
        }
    }
    结果：
    ---------------- 默认 排序结果-----------------
    a : 1
    b : 1
    bb : 1
    c : 1
    ---------------- 自定义 排序结果-----------------
    c : 1
    bb : 1
    b : 1
    a : 1
```

```java
// 字典序数据结构
private static class TrieTree {
    TrieTree[] next = new TrieTree[2];
    int count = 1;
}

Scanner sc = new Scanner(System.in);
    while (sc.hasNext()) {
            //* Scans the next token of the input as an <tt>int</tt>.
        int n = sc.nextInt();
        int m = sc.nextInt();
        int[] a = new int[n];
        for (int i = 0; i < n; i++) {
            a[i] = sc.nextInt();
        }
        System.out.println(solve(a, m));
    }
// 取出int型数据的每一位，从高位到低位
int a;
for (int j = 31; j >= 0; j--) {
                int digit = (a >> j) & 1; 
}
```