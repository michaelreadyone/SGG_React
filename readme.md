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
  - Babel.min.js
    - 将ES6转化为ES5的语法，让浏览器读懂
    - 解读import语句
    - 将jsx转化为js，让浏览器读懂
  - React.development.js
    - React核心，用户通过它操作React虚拟DOM
  - React-dom.development.js
    - React扩展库，通过这个去操作正式DOM
- 003 为什么要用 jsx创建虚拟dom 而不是 js：
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
  1.定义虚拟DOM时，不要写引号。
  2.标签中混入JS表达式时要用{}。
  3.样式的类名指定不要用class，要用className。
  4.内联样式，要用style={{key:value}}的形式去写。
  5.只有一个根标签
  6.标签必须闭合
  7.标签首字母
      (1).若小写字母开头，则将该标签转为html中同名元素，若html中无该标签对应的同名元素，则报错。
      (2).若大写字母开头，react就去渲染对应的组件，若组件没有定义，则报错。
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
- 007 React组件与模块
  - React组件 Component：
    - 将html，css，js打包成一个小组件
    - 更好的结构化，代码复用性
- 008 安装chrome react 开发者工具
  - Components:显示页面中React组件
  - Profiler: 查看网站的性能（渲染了多久，每个组件的加载速度，加载速度慢的原因。。。）
- 009 函数式组件
- 010 复习类
  - 一般方法的speak() 为什么在函数打印里没有显示？它放在了哪里？
  - p1.speak.call() 这个call函数怎么用？
- 011 类式组件
- 012 对state的理解
  - 是React制作组提前写好的一个React.Component的属性
- 013 初始化state
  - 在类组件中使用constructor
- 014 React中的事件绑定
  - 原始js中的事件绑定
- 015 类方法中的this
  - 注意原型，弄清楚一般方程是附在类的原型上
- 016 解决类中this指向问题
  - [bind()的用法](<https://www.runoob.com/w3cnote/js-call-apply-bind.html>)
  - call, apply, bind 都可以用来改变this的指向。
- 017 setState的使用 
  - 数据的变化是如何驱动界面的变化的？
  - React不认同你用js自行更改status里的量，
  - 需要使用React制定的方法（内置的API： setState）
  - setState的语句是替代还是合并？如果只传state里的一个状态，其他状态是否还在？
    - 是合并
  - React承诺，只要按照合法的形式更新status，它就会调用render()来重新渲染页面
  - 为什么要写构造器？
    - 在构造器里初始化状态
    - 解决this的指向问题
- 018 state 的简写方式
  - 怎么在不写constructor的情况下，追加新的变量呢？
- 019 总结state
  - stated 的值是对象（k:v)的组合
  - 组件通过state的改变来重新渲染，render页面
  - 组件render()中的this是组件示例对象
  - 自定义方法的this是undefined
  - 状态数据不能直接修改，必须用setState()去修改
- 020 props
  - React 自带的一个重要属性，通过标签属性发方式传入
- 021 批量传递props
  - 使用{...p} 放进组件标签来传递
  - ...运算符的复习，ES6 reduce的用法
  - 组件里的{...p} 和js里的{...p}不是一个意思。...是不能打开对象的，js里加{}就可以复制这个对象，而组件里的{...p}是通过babel和React来重新解读的，仅仅用于标签属性的传递。不能用在其他地方。比如在组件里console.log()是打印不出来东西的。
  - js的{...p,name:'jack}还有更新合并的功能
- 022 对于props的类型限制
  - 某一prop的制定默认值
  - 对于某一prop只允许特定的type，比如Number
  - 必须要求某一prop有传入值
  - 对传入函数的限制
    - 在React15及以前，使用React.PropTypes
    - 在React16以后，这个module被分离出来了，就是prop-tyoes.js 要导入后直接使用PropTypes
- 023 props的简写方式
  - props是只读的
  - 使用 static， 是变量成为class 变量，而非实例变量
- 024 类式组件中的构造器与props
  - 构造器中的props传给和不传给super()有什么区别吗？
  - 类中的构造器到底有什么作用呢？
  - 如果需要写构造器，那么就要一定接和传props
- 025 函数组件使用props
  - 类式组件的state和refs不能用在function组件里，但是props可以
- 026 props总结 明天看
- 027 字符串形式的ref
  - 打标识（ref)的tag都会被收集到react的refs里
  - &nbsp: non-breaking space
  - 类似于html的id，迅速找到一个reference，可以调取它的内部值，或者干其他事情
  - ref收集的不是虚拟dom，而是由虚拟DOM转化成的真实DOM
  - 官方已经不推荐使用
  
- 028 回调形式的ref
  - 回调函数的三特点
    - 你定义了函数
    - 你没有调用函数
    - 别人调用的函数
  - 在ref里写一个回调函数，然后react去调用，参数就是这个ref所在的节点
  - React只调用名为ref的函数，你写个名为haha的函数，react是不会调用的
- 029 回调ref中调用次数的问题
  - 内连的回调和内绑定回调的区别
- 030 createRef
  - 这是一人一份的，如果写2次就会overwrite
- 031 总结Ref
  - 不要过渡使用Ref
- 032 React中的时间处理
  - 不要过渡的使用Ref
  - 可以避免的情况
    - 发生事件的元素也是操作时间的元素时，可以使用event.target