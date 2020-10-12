---
layout: post
title: java
tags: java
categories: java
---
### learn in work
#### 定时任务
```
ScheduledExecutorService executorService=new ScheduledThreadPoolExecutor(1);
        executorService.scheduleWithFixedDelay(new Runnable() {
            @Override
            public void run() {
                System.out.println( new Date());
            }
        },1000, 5000, TimeUnit.MILLISECONDS); // 1000  初始化开始时间   5000 间隔时间
```