---
title: 对修饰器的实验支持...experimentalDecorators
categories: Exceptions
---

## 异常描述

对修饰器的实验支持是一项将在将来版本中更改的功能。设置+"experimentalDecorators"+选项以删除此警告。

## 异常场景

VSCode  添加的Vue 组件。

```vue
@Component
export default class HelloWorld extends Vue {
```



## 解决方案

项目目录下 添加 tsconfig.json	

```json
{
  "compilerOptions": {
    "experimentalDecorators": true,
  },
  "include": ["src/**/*.tsx"],
}
```

说明：include 一定要包含 tsx文件所在的目录



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



##### 参考资料

https://blog.csdn.net/weixin_33834075/article/details/88625659 