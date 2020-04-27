---
title: A 标签锚点路由# 处理
categories: Exceptions
date: 2020-04-08 15:35:110


---

## 异常描述

当页面通过A标签点击，创建锚点到对应元素上。此时路由会变更增加“#”。



## 解决方案

首先A标签点击不出现路由更改，就取消Href属性，其次通过document.querySelector(`#${id}`) 获取要到达的元素对象，然后通过元素scrollIntoView(true)方法进行锚点效果。