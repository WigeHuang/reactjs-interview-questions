# javascript 基础
- 1. 原型链
```
每个实例对象（object）都有一个私有属性（称之为 __proto__ ）指向它的构造函数的原型对象（prototype）。该原型对象也有一个自己的原型对象（__proto__），层层向上直到一个对象的原型对象为 null。
```
- 2. 闭包，闭包的优缺点
```
当函数中的函数持有了上层函数的变量的引用，而函数本身定义在上层函数里面，他们之间的作用域相互引用，这个时候把这个函数和它持有的引用称为闭包。
优点是是可以避免全局变量的污染;缺点是引用的变量太大会造成内存泄漏问题。
```
- 3. 常见es6 API
```
结构，展开，类，箭头函数，数组扩展：from,includes,find 对象扩展：keys,values, for of, generator 函数，promise
```
- 4. 克隆
- 5. 数组排序
- 6. javascript event loop
- 7. typescript 常用的特性(加分）
- 8. promise
- 9. 数组去重
```
Promise 是异步编程的一种解决方案,为了避免回调地狱
```

# css 基础
- 1. 盒子模型
- 2. 垂直水平居中的各种写法
- 3. 常用选择器


# 浏览器方面
- 1. http 请求方法，post,get 的区别,RESTful API
- 2. http 状态码
- 3. 从浏览器在地址栏输入地址敲下回车到页面渲染经过了哪些流程
```
1、浏览器的地址栏输入URL并按下回车。
　　2、浏览器查找当前URL的DNS缓存记录。
　　3、DNS解析URL对应的IP。
　　4、根据IP建立TCP连接（三次握手）。
　　5、HTTP发起请求。
　　6、服务器处理请求，浏览器接收HTTP响应。
　　7、渲染页面，构建DOM树，CSS规则树，两者结合生成渲染树，加上layout 规则确定每个元素的位置，最后绘制。
　　8、关闭TCP连接（四次挥手）。
```

# 优化方面
- 1. 节流 和 消抖
```
节流: 使得一定时间内只触发一次函数 例如：scroll 事件，单位时间后计算一次滚动位置
消抖: 将多次操作合并为一次操作进行 例如：模糊搜索框
```
- 2. 压缩 和 CDN
- 3. 按需引用

# 兼容方面
- 1. postcss 加前缀
- 2. js pollyfills


# 主流框架 react
- 1. virtual diff 算法 和 key 的优化原理
```
计算出Virtual DOM中真正变化的部分，并只针对该部分进行原生DOM操作，而非重新渲染整个页面
同级节点的对比策略可以极大的简化 diff 算法，减少对 DOM 的操作 例如删除列表前面的元素，diff会认为后面的都发生更新，而加了key
通过移动元素而不是修改元素来达到更新的目的。为了告诉程序要怎么移动元素，我们必须给每个元素加上一个唯一标识，也就是key通过对比找出真正需要删除的元素，直接删除，而不操作别的元素。
```

- 2. setState 同步和异步问题
```
setState本身并不是异步,只是因为react的性能优化机制体现为异步.在react的生命周期函数或者作用域下为异步,在原生的环境下为同步.
```

- 3. react 常见的生命周期 16.3以前 和 16.3 以后
```
getSnapshotBeforeUpdate(prevProps, prevState) 介于rerender 和 didUpdate 之间，
用于返回更新之前的dom的快照
getDerivedStateFromProps(props,state) 相当于componentWillmount 和 componentWillReceiveProps合并
用于将props 值映射为 state，没有变化返回null
```

- 4. 钩子组件和类组件的区别
- 5. redux 的基本流程
- 6. 服务端渲染原理(加分)
- 7. HOC ,render props, forwardRef, ref
- 8. react 首次查询为啥要放在 didMount 里面
```
因为react didMount 是确定在首次渲染后只会执行一次的周期函数
```

=========================以下不是核心===============================
# 项目管理相关
- 开发工作流工具
- git 版本控制工具常用命令

# 运维相关
- 1. 跨域问题
- 2. 自动化部署
- 3. docker(加分）

# 后端相关（加分）
- 1. nodejs 等后端操作基本会用
- 2. 懂数据库基本知识
