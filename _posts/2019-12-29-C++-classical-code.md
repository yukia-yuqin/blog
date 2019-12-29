---
layout: post
title: C++经典代码
tags: code
categories: code
---
since 2019-6-29
经典流传<br>
<br>





### C++
- 写dp的时候，两重循环，第一层循环控制距离，第二层循环控制行号
- C++
```C++
    unordered_set<string> dict(wordDict.cbegin(), wordDict.cend());  //mark

```
- C++
``` C++
    #define random(x) (rand()%x) 返回一个[0,x)之间的整数
    rand() 返回一个0至RAND_MAX (stdlib.h) 2147483647间的随机数
```

``` C++
    vector<vector<int>> _m;
    _m = vector<vector<int>>(n, vector<int>(n, INT_MIN));  //mark

```
- 一点点
``` C++
    sort(ins.begin(), ins.end(), [](vector<int> a, vector<int> b){return a[0] < b[0];}
    unique函数返回去重后最后一个元素迭代器
    Trie这么写
    vector<bool> passed(n, false)
    stringstream
    inplace_merge(begin, mid, right);
```

- C++命名规范 [google]
    - 函数命名, 变量命名, 文件命名要有描述性;
    - 文件名要全部小写, 可以包含下划线 (_) 或连字符 (-), 依照项目的约定. 如果没有约定, 那么 “_” 更好.
    - 类型名称的每个单词首字母均大写, 不包含下划线: MyExcitingClass, MyExcitingEnum.
    - 变量 (包括函数参数) 和数据成员名一律小写, 单词之间用下划线连接. 类的成员变量以下划线结尾, 但结构体的就不用, 如: a_local_variable, a_struct_data_member, a_class_data_member_.
    - 不管是静态的还是非静态的, 类数据成员都可以和普通变量一样, 但要接下划线。  string table_name_;  // 好 - 后加下划线. string tablename_;   // 好.static Pool<TableInfo>* pool_;  // 好.
    - 结构体变量 
    - 常量命名 const int kDaysInAWeek = 7; 声明为 constexpr 或 const 的变量, 或在程序运行期间其值始终保持不变的, 命名时以 “k” 开头, 大小写混合. 例如:
    - 函数命名。常规函数使用大小写混合, 取值和设值函数则要求与变量名匹配: MyExcitingFunction(), MyExcitingMethod(), my_exciting_member_variable(), set_my_exciting_member_variable().
    - 7.7. 命名空间命名
    ```C++
    class Solution {
    public:
        int KthSmallest(vector<vector<int>>& matrix, int k) {
            int n = matrix.size() - 1;
            int le = matrix[0][0], ri = matrix[n][n];
            while (le < ri) {
                int mid = le + (ri - le) / 2;
                int lt_count = 0;
                for (int i = 0; i <= n; i++) {
                    lt_count += upper_bound(matrix[i].begin(), matrix[i].end(), mid) - matrix[i].begin();
                }
                if (lt_count < k) {
                    le = mid + 1;
                } else {
                    ri = mid;
                }
            }
            return le;
        }
    };
    ```
- 常用C++ code 在线编程
```C++
    auto it = lower_bound(res.begin(), res.end(), i); 
    if (it == res.end()) {
    #define A(i) nums[(1+2*(i)) % (n|1)]  // 天哪，神来之笔，，，，
```
```C++
    class disjoint_set {
        vector<int> v;
        int sz;
        public:
        disjoint_set(int n) {
            makeset(n);
        }

        void makeset(int n) {
            v.resize(n);
        // std::iota :用顺序递增的值赋值指定范围内的元素 。
            iota(v.begin(), v.end(), 0);
            sz = n;
        }

        int find(int i) {
            if (i != v[i])
                v[i] = find(v[i]);
            return v[i];
        }
        
        void join(int i, int j) {
            int ri = find(i), rj = find(j);
            if (ri != rj) {
                v[ri] = rj;
                sz--;
            }
        }
        
        int size() {
            return sz;
        }
    };

```
- C++格式
    - 若用引用捕获, 在变量名和 & 之间不留空格.auto add_to_x = [&x](int n) { x += n; };
    - if (condition) {  // 好 - IF 和 { 都与空格紧邻.
    - :左边 ;左边 (右边 )左边
    ``` C++
    if (b) {          // if 条件语句和循环语句关键字后均有空格.
    } else {          // else 前后有空格.
    }
    while (test) {}   // 圆括号内部不紧邻空格.
    for (int i = 0; i < 5; ++i) {
    switch (i) {
    case 1:         // switch case 的冒号前无空格.
        ...
    case 2: break;  // 如果冒号有代码, 加个空格.
    x = 0;     // 赋值运算符前后总是有空格.
    // 其它二元操作符也前后恒有空格, 不过对于表达式的子式可以不加空格.
    // 圆括号内部没有紧邻空格.
    v = w * x + y / z;
    v = w * (x + z);
    // 在参数和一元操作符之间不加空格.
    x = -5;
    ++x;
    if (x && !y)
    // 尖括号(< and >) 不与空格紧邻, < 前没有空格, > 和 ( 之间也没有.
    vector<string> x;
    y = static_cast<char*>(x);
    // 在类型与指针操作符之间留空格也可以, 但要保持一致.
    vector<char *> x;
    ```
    - ./-> 操作符前后不留空格, */& 不要前后都留, 一个就可, 靠左靠右依各人喜好;

- C++ 常用容器
```C++
    // 无序集合
    unordered_set<string> d(wordList.begin(), wordList.end());
    d.erase(head);
    // 双端队列
    deque<string> dq;
    string head = dq.front();
    dq.pop_front();        
```
- 并查集 https://www.jianshu.com/p/def7767982ac
```C++
    private int count;
    private int[] parents;
    
    //初始化并查集
    public void initUnionFind(int m, int n, char[][] grid){
        parents = new int[m*n];
        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){
                if(grid[i][j] == '1'){
                    count++;
                }
                parents[i*n+j] = i*n+j;
            }
        }
    }
    
    public int find(int idx){
        while(idx != parents[idx]){
            //在查找的过程中压缩路径,减少查找的次数
            parents[idx] = parents[parents[idx]];
            idx = parents[idx];
        }
        return idx;
    }
 
    public void union(int p, int q){
        int pRoot = find(p);
        int qRoot = find(q);
        //两个元素的根不同,则合并
        if(pRoot != qRoot){
            parents[qRoot] = pRoot;
            count--;
        }
    }
    
    public boolean isConnected(int p, int q){
        int pRoot = find(p);
        int qRoot = find(q);
        
        //两点不连通
        if(pRoot != qRoot){
            return false;
        }
        return false;
    }
```
```位运算
    <!-- 求异或的结果 -->
    int diff = accumulate(nums.begin(), nums.end(), 0, bit_xor<int>());
    <!-- 求diff这个数的最末一位不为0的位置 -->
    diff &= -diff;

```

- sort 内部写一个比较器
```C++
    sort(numbers.begin(),numbers.end(),[](const int s1,const int s2){
                return to_string(s1)+to_string(s2) < to_string(s2) + to_string(s1);
            });
    or
    struct Comp {
        bool operator()(const pair<int, string>& lhs, const pair<int, string>& rhs) const {
            if (lhs.first != rhs.first)
                return lhs.first < rhs.first;
            return lhs.second > rhs.second;
        }
    };       
    priority_queue<pair<int, string>, vector<pair<int, string>>, Comp> Q;

```

- C++ 分割字符串 变为stringstream
```C++
    stringstream ss(path);
	while(getline(ss,tmp,'/')) {
		if (tmp == "" or tmp == ".") continue;
```
- C++ make_pair,queue.front().first,return {},pair<TreeNode* ,int>
```C++
    if(root == NULL) return {};
    queue<pair<TreeNode *, int>> q;
    q.push(make_pair(root,0));
        TreeNode * t = q.front().first;
        q.pop();
            res.push_back({t->val});
            res[level].insert(res[level].begin(),t->val);
```

``` C++
    // - C++ 实现自定义字符串比较函数
    static bool sortCom(const string &a, const string &b) {
        return (a+b) > (b+a);
    }
    sort(arr.begin(), arr.end(), sortCom);

    // vector , deque, pair 相关
    deque<pair<int, int>> queue;
    queue.push_back(make_pair(i,j));
    int curi = queue.front().first, curj = queue.front().second;
    queue.pop_front();
    
    // 按照vector<pair<int, int>> 中两个数的比值排序
    typedef pair<int, int> pii;
    bool piisort(pii a, pii b) {
        // a.first / a.second > b.first / b.second
        return a.first * (ll)b.second > a.second * (ll)b.first;
    }
```




- C++ 实现tire树
```C++
    class TireNode {
    public:  //注意这里应该是public:
        char value;
        bool isend;
        vector<TireNode *> next;
        TireNode(): value(' '), isend(false){};  //注意这里使用初始化表来初始化对象
        TireNode(char v): value(v), isend(false){};
        TireNode* subNode(char c) {
            if(!next.empty()){
                for(auto child: next) {
                    if(child->value == c) {
                        return child;
                    }
                }
            }
            return nullptr;
        }
        ~TireNode(){
            for(auto child: next) 
                delete(child);
        }
    };

    class Trie {
    private:
        TireNode* root;
    public:
        /** Initialize your data structure here. */
        Trie() {
            root = new TireNode();
        }
        
        /** Inserts a word into the trie. */
        void insert(string word) {
            TireNode* cur = root;
            int i = 0;
            for( ; i < word.size(); i++) {
                TireNode* curNext = cur->subNode(word[i]);
                if (curNext) {
                    cur = curNext;
                } else {
                    break;
                }
            }
            if (i >= word.size()) {
                cur->isend = true;
            } else {
                for ( ; i < word.size(); i++) {
                    TireNode* newNode = new TireNode(word[i]);
                    cur->next.push_back(newNode);
                    cur = cur->subNode(word[i]);
                }
            }
            cur->isend = true;
        }
        
        /** Returns if the word is in the trie. */
        bool search(string word) {
            TireNode* cur = root;
            for (int i = 0; i < word.size(); i++) {
                TireNode* curNext = cur->subNode(word[i]);
                if (curNext) {
                    cur = curNext;
                } else {
                    return false;
                }
            }
            return cur->isend;
        }
        
        /** Returns if there is any word in the trie that starts with the given prefix. */
        bool startsWith(string word) {
            TireNode* cur = root;
            for (int i = 0; i < word.size(); i++) {
                TireNode* curNext = cur->subNode(word[i]);
                if (curNext) {
                    cur = curNext;
                } else {
                    return false;
                }
            }
            return true;
        }

    };

    /**
    * Your Trie object will be instantiated and called as such:
    * Trie* obj = new Trie();
    * obj->insert(word);
    * bool param_2 = obj->search(word);
    * bool param_3 = obj->startsWith(prefix);
    */
 ```