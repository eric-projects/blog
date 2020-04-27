---
title: CheckBox 组件点击后无效
categories: Exceptions
date: 2019-10-22 13:53:19
---

## 异常描述

Ant-Design Vue中 CheckBox组件勾选后无效。 

## 解决方案

数据是变化的，原来是数据类型不匹配。比如：any 中的 string类型，与 "number"|"string" 类型中的 number。







