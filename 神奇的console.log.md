---
title: Console.log 数据无变化问题
categories: Exceptions
date: 2019-01-09 17:34:21
---

## 异常描述

浏览器控制台Console打印变量，不同时间看到的值有所不同。



## 解决方案

控制台看到的数据是否一至，取决于你什么时候去看console的数据。

console.log(a) // a={“A”:1}

console.log(a) // a={"B":2}

如果最后查看，那么看到的都会是 a={"B":2}；

如果第一次Console后直接查看，那么两次看到的就是不一样。







