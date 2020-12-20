---
layout: post
title: javascript
tags: javascript
categories: javascript

---

### 学习连接

-  [ECMAScript 6 入门](https://es6.ruanyifeng.com/) https://es6.ruanyifeng.com/#docs/intro
-  可以搜索javascript https://developer.mozilla.org/
-  

### 简介

- **ES6**是`ECMA`为`JavaScript`制定的第6个标准版本，相关历史可查看此章节[《ES6-ECMAScript6简介》](https://link.zhihu.com/?target=https%3A//es6.ruanyifeng.com/%23docs/intro)。

- 该标准从一开始就是针对 JavaScript 语言制定的，但是之所以不叫 JavaScript，有两个原因。一是商标，Java 是 Sun 公司的商标，根据授权协议，只有 Netscape 公司可以合法地使用 JavaScript 这个名字，且 JavaScript 本身也已经被 Netscape 公司注册为商标。二是想体现这门语言的制定者是 ECMA，不是 Netscape，这样有利于保证这门语言的开放性和中立性。

  因此，ECMAScript 和 JavaScript 的关系是，前者是后者的规格，后者是前者的一种实现（另外的 ECMAScript 方言还有 JScript 和 ActionScript）。日常场合，这两个词是可以互换的。

### 语法

- **Promise**

  - promise 对象用于表示一个异步操作的最终完成 (或失败)及其结果值。

- improt 

  - 是默认导出就要不加{}，其他就需要加{}

- 路径

  - ```css
    @import '../../../../assets/css/varibles.scss'
    ```

    **可以简写为以下：**

    ```css
    @import '~@/assets/css/varibles.scss'
    ```

### VUE

- 文件扩展名为 `.vue` 的 **single-file components (单文件组件)** 为以上所有问题提供了解决方法，并且还可以使用 webpack 或 Browserify 等构建工具。

- vue || 用法说明

  var temp = str1 || str2;
  当str1是undefined、null或""时，temp = str2;
  当str1是非空或非undefined时，temp = str1;

- 为自定义组件绑定原生事件必须使用 .native 修饰符，只有Button 组件可以监听 click 事件。

### VUEX

- Vuex 是一个专为 Vue.js 应用程序开发的**状态管理模式**。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。Vuex 也集成到 Vue 的官方调试工具 [devtools extension (opens new window)](https://github.com/vuejs/vue-devtools)，提供了诸如零配置的 time-travel 调试、状态快照导入导出等高级调试功能。