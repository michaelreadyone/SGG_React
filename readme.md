# 2021 React 全家桶

- 001 React 简介
    - 什么是React
        用于构建用户的界面JavaScript库，

        做第三步
        1，发送请求获取数据
        2，处理数据（过滤，整理格式等）
        3，操作DOM呈现页面

        React是一个将数据渲染为HTML试图的开源JavaScript库
    - 为什么要学
      1. 原生JS操作DOM繁琐，效率低。编码繁琐，每一次操作，浏览器都要绘制，排列，干活。这种模式相当于使用DOM-API操作UI，想象一下一个动作：让一个box 3秒后变一个颜色 
      2. 使用JS直接操作DOM，浏览器大量重绘重排
      3. 原生JS没有组件化方案，代码复用率低
    - React 特点
      1. 采用**组件化**模式，**声明式**编码，提高效率，组件复用率
          1. 声明式：不明确的指示每一个细节。high level的指挥
      2. React Native 移动端开发
      3. 使用**虚拟DOM**+优秀的**Diffing算法**，尽量减少与真实DOM的交互
    - 学前必备知识：
      - 判断this的指向
      - class（类）
      - ES6语法规范
      - npm包管理器
      - [原型，原型链](https://www.youtube.com/watch?v=L5OFEmqaoXg)
      - 数组常用方法
      - 模块化
- 002 Hello React
- 003 为什么要用 jsx 而不是 js：
  - 是为了解决原始 js 创建虚拟 dom 的繁琐，相当于 jsx 是 js 的语法糖
  - Babel 把 jsx 翻译成了 js
- 004 虚拟 DOM 是什么呢？
  - 通过 console 打印我们发现它不是很复杂，就是一个一般对象（Object)
  - 代码里加 debugger 可以在浏览器里通过鼠标 hover 查看变量的细节
  - 和真实 DOM 的比较
    - 虚拟 DOM”轻“
    - 真实 DOM”重“
    - 因为虚拟 DOM 只是 React 内部用，不需要真实 DOM 上那么多的属性，比如 get 属性，修改属性的 API。
  - 虚拟 DOM 最终会被 React 转化为真实 DOM，呈现在页面上
- 005 React jsx 语法规则
  - jsx： javascript xml
- 006 jsx 练习
  - jsx 里能混入的是 js 的表达式，而不是代码语句
    - 一个表达式产生一个值，可以放在任何一个需要值的地方
    - 简单区分的表达式和语句的方法是：看看左边能不能接

        ```javascript
        const x = (表达式/代码语句)
        ```
    - 为什么jsx里的item需要unique key？
      - 因为jsx需要用这个来算diffing
      - 暂时使用idx来作为key，但是这个方法有的时候会出问题，详细的情况会在后面说。