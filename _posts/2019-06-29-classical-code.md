---
layout: post
title: 经典代码
tags: interview common
categories: interview
---

经典流传<br>
<br>

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
- sort 内部写一个比较器
```C++
sort(numbers.begin(),numbers.end(),[](const int s1,const int s2){
            return to_string(s1)+to_string(s2) < to_string(s2) + to_string(s1);
        });
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
- C++ 初始化一个数组
```C++
int memo[n+1] = {0};
```
###java
- 单例模式
```java
class WordVec2DocVec{
    private static volatile WordVec2DocVec instance = null;

    public static WordVec2DocVec getInstance() {
        if (instance == null) {
            synchronized (WordVec2DocVec.class) {
                if (instance == null) {
                    instance = new WordVec2DocVec();
                }
            }
        }
        return instance;
    }
}
 WordVec2DocVec.getInstance()
```
- 列表排序
```java
	List<Pair<String, Double>> cidSore = Lists.newArrayList();
	cidSore.add(Pair.of(fid, tsum));
	 cidSore.sort((o1, o2) -> o2.getRight().compareTo(o1.getRight()));
	
	List<Pair<String, Integer>> lst = Lists.newArrayList();
	lst.add(Pair.of(entry.getKey(), entry.getValue()));
	lst.sort((x, y) -> Integer.compare(y.getValue(), x.getValue()));
```
- map排序
```java
	private static Map<String, Float> sortByValue(Map<String, Float> unsortMap) {
	        List<Map.Entry<String, Float>> list =
	                new LinkedList<Map.Entry<String, Float>>(unsortMap.entrySet());
	        Collections.sort(list, new Comparator<Map.Entry<String, Float>>() {
	            public int compare(Map.Entry<String, Float> o1,
	                               Map.Entry<String, Float> o2) {
	                return (o2.getValue()).compareTo(o1.getValue());
	            }
	        });
	        Map<String, Float> sortedMap = new LinkedHashMap<String, Float>();
	        for (Map.Entry<String, Float> entry : list) {
	            sortedMap.put(entry.getKey(), entry.getValue());
	        }
	        return sortedMap;
	    }
```
```java
Comparator<Pair<String, Double>> OrderIsdn = new Comparator<Pair<String, Double>>() {
    public int compare(Pair<String, Double> o1, Pair<String, Double> o2) {
        // TODO Auto-generated method stub
        double numbera = o1.getRight();
        double numberb = o2.getRight();
        if (numberb < numbera) {
            return 1;
        } else if (numberb > numbera) {
            return -1;
        } else {
            return 0;
        }
        Queue<Pair<String, Double>> priorityQueue = new PriorityQueue<>(100, OrderIsdn);
        ListIterator<Pair<String, Double>> lit = recList.listIterator();
            while (lit.hasNext()) {
                lit.next();
            }
        while (lit.hasPrevious()) {
                Pair<String, Double> litCur = lit.previous();
        }
    }
}
```
- 写文件
```java
FileOutputStream fos = new FileOutputStream("../data/" + fname);
OutputStreamWriter osw = new OutputStreamWriter(fos);
BufferedWriter bw = new BufferedWriter(osw);
bw.write(mapper.writeValueAsString());
```
- 解析json
```java
JSONObject jsonObj = new JSONObject(retOpt.get().toString());
    if (jsonObj.has("result")) {
        String result = jsonObj.get("result").toString();
        JSONObject posObj = new JSONObject(result.substring(1, result.length() - 1));
        if (posObj.has("pos_content")) {
            String posContent = posObj.get("pos_content").toString();
            return getArticleFeature(posContent);
        }
    }
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

### Spark
```scala


### docker
- 一些没有用上的
```shell
.\certutil.exe -addstore -f "my" "MtutorKVcert.cer"
.\certutil.exe -p Mtutorkv@47 -importPFX -f "my" "MtutorKVcert.pfx" 
.\certutil.exe -store "my"

xcopy D:\code\mTutor\main\service\csx\DevDeploy\roles\*.cmd C:\Users\v-yuqwan\Desktop\tmp\
ICACLS c:\vdata\MtutorKVcert.cer /grant "IIS AppPool\DefaultAppPool":F
ICACLS c:\vdata\MtutorKVcert.pfx /grant "IIS AppPool\DefaultAppPool":F
icacls c:\inetpub\wwwroot\ /grant "IIS AppPool\DefaultAppPool:F"
icacls C:\ProgramData\Microsoft\Crypto\RSA\MachineKeys /t /grant "IIS AppPool\DefaultAppPool:(OI)(CI)F"
winhttpcertcfg.exe -g -a "IIS AppPool\DefaultAppPool" -c LOCAL_MACHINE\MY -s MtutorKVcert
icacls C:\inetpub\wwwroot\App_Data\Runtime /t /grant "IIS AppPool\DefaultAppPool:(OI)(CI)F"
```

- build and run docker
```shell
docker build -t bmtutor .
docker rm -f dmtutor
docker run -it ^
    -v D:\code\codevolume\:C:\inetpub\wwwroot-copy ^
    -v D:\code\dockervolume\:C:\vdata ^
    -p 81:80 --rm --name dmtutor bmtutor
```

- 进入docker环境
```shell
docker exec -it dmtutor cmd
```

- 常见的shell命令
```shell
dir .|  find "Microsoft.WindowsAzure.ServiceRuntime.dll"
dir .|  find "System.Web.Http.WebHost.dll"

D:\code\mTutor\main\service\csx\DevDeploy\roles\MTutor.Service.Web\
D:\code\dockervolume\

xcopy C:\vdata\codevolume\* C:\inetpub\wwwroot\ /e
cd C:\inetpub\logs\LogFiles\W3SVC1  
cd C:\vdata

xcopy C:\inetpub\wwwroot\* C:\inetpub\wwwroot\ /s /h /d /y
docker run -it -v D:\code\codevolume\:C:\inetpub\wwwroot-copy -v D:\code\dockervolume\:C:\vdata -p 81:80 --rm --name dmtutor bmtutor
```

- dockerfile编写
```shell
#Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
#For more information, please see http://aka.ms/containercompat 


# FROM mcr.microsoft.com/dotnet/framework/sdk:4.8 AS build
# WORKDIR /app

# # copy csproj and restore as distinct layers
# COPY *.sln .
# COPY MTutor.Service.Web/*.csproj ./MTutor.Service.Web/
# COPY MTutor.Service.Web/*.config ./MTutor.Service.Web/
# RUN nuget restore

# # copy everything else and build app
# COPY MTutor.Service.Web/. ./MTutor.Service.Web/
# WORKDIR /app/MTutor.Service.Web
# RUN msbuild /p:Configuration=Release


# FROM mcr.microsoft.com/dotnet/framework/aspnet:4.8 AS runtime
# WORKDIR /inetpub/wwwroot
# COPY --from=build /app/MTutor.Service.Web/. ./

FROM mcr.microsoft.com/dotnet/framework/aspnet:4.6.2 AS runtime
EXPOSE 80
WORKDIR /inetpub/wwwroot
COPY ./MTutor.Service.Web/approot/ ./
# VOLUME D:\\code\\codevolume\\:C:\\inetpub\\wwwroot-copy
# VOLUME D:\\code\\dockervolume\\:C:\\vdata
# COPY D:\code\codevolume\ C:\inetpub\wwwroot-copy\
# COPY D:\code\dockervolume\ C:\vdata\
# COPY pre-run.cmd .
COPY run.cmd .
ENTRYPOINT [ ".\\run.cmd" ]
```

- msbuild publish
```shell
@ECHO ------ Build start ------
CD /d D:\code\mTutor\main\service
MSBuild.exe /t:Publish /p:Configuration=DevDeploy /p:TargetProfile=Local .\MTutor.Service.sln
XCOPY C:\Users\v-yuqwan\Desktop\tmp\* D:\code\mTutor\main\service\csx\DevDeploy\roles\
DEL /F /S /Q D:\code\codevolume\*
XCOPY D:\code\mTutor\main\service\csx\DevDeploy\roles\MTutor.Service.Web\approot\* D:\code\codevolume\  /s /h /d /y
PAUSE
```

