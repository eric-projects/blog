---
title: JSX 元素隐式具有类型 "any"...
categories: Exceptions
---

## 异常描述

JSX 元素隐式具有类型 "any"，因为不存在接口 "JSX.IntrinsicElements"。



## 异常场景

Vue中 html元素不识别 <div>

```html
 public render() {
    return <div>Hello Word</div>;
  }
```

## 解决方案
需要在 tsconfig.json 中指定包含的 .tsx文件

```json
 {
  "include": [
    "components/**/*.ts",
    "components/**/*.tsx",
    "components/**/*.vue"
  ],
 }
```



说明：vue项目中的 `shims-tsx.d.ts` 才是至关重要的

```json
import Vue, { VNode } from 'vue';

declare global {
  namespace JSX {
    // tslint:disable no-empty-interface
    interface Element extends VNode {}
    // tslint:disable no-empty-interface
    interface ElementClass extends Vue {}
    interface IntrinsicElements {
      [elem: string]: any;
    }
  }
}
```



 **更新**：

项目下建立types 放入.d.ts文件

然后添加到 tsconfig.json 的include中

```
---types
  --- shims-tsx.d.ts
  --- shims-vue.d.ts
  
 "include": [
    xxx
    "types/**/*.ts"
  ],
```

