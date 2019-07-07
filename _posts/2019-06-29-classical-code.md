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

