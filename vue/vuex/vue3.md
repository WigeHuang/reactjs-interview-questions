1、vue3的新特性
答：
1、响应系统的变动
由原来的Object.defineProperty 的getter 和 setter，改变成为了ES2015 Proxy 作为其观察机制。
Proxy的优势：消除了以前存在的警告，使速度加倍，并节省了一半的内存开销。
2、虚拟DOM重写（Virtual DOM Rewrite）
虚拟 DOM 从头开始重写，我们可以期待更多的编译时提示来减少运行时开销。重写将包括更有效的代码来创建虚拟节点。
3、组件渲染的优化（优化插槽生成）
Vue2当中在父组件渲染同时，子组件也会渲染。 Vue3就可以单独渲染父组件、子组件。
4、静态树提升（Static Tree Hoisting）
使用静态树提升，这意味着 Vue 3 的编译器将能够检测到什么是静态组件，然后将其提升，从而降低了渲染成本。它将能够跳过未整个树结构打补丁的过程。


静态树提升（.png
5、静态属性提升（Static Props Hoisting）
此外，我们可以期待静态属性提升，其中 Vue 3 将跳过不会改变节点的打补丁过程。
总体来说：1. 更快 2. 更小 3. 更容易维护 4. 更加友好 5. 更容易使用

2.vue3对比vue2有哪些不同？
答： https://www.cnblogs.com/ygunoil/p/14463855.html
3、Proxy 相比于 defineProperty 的优势
Object.defineProperty() 的问题主要有三个：
不能监听数组的变化
必须深层遍历嵌套的对象
必须遍历对象的每个属性
Proxy 在 ES2015 规范中被正式加入，它有以下几个特点：
针对对象：针对整个对象，而不是对象的某个属性，所以也就不需要对 keys 进行遍历。这解决了上述 Object.defineProperty() 第二个问题
* 支持数组：Proxy 不需要对数组的方法进行重载，省去了众多 hack，减少代码量等于减少了维护成本，而且标准的就是最好的。
除了上述两点之外，Proxy 还拥有以下优势：
Proxy 的第二个参数可以有 13 种拦截方法，这比起 Object.defineProperty() 要更加丰富
Proxy 作为新标准受到浏览器厂商的重点关注和性能优化，相比之下 Object.defineProperty() 是一个已有的老方法。
4、vue2为什么不使用proxy？
答： 兼容性
5、vue3性能比vue2好的原因？
答：1.diff算法优化
2.静态提升hoistStatic
3.事件侦听器缓存 cacheHandles
* 
* 目录++++++++++++++++++++
  ├─public
  │      favicon.ico
  │      index.html
  └─src
  │  App.vue
  │  main.ts
  │  shims-vue.d.ts
  ├─assets
  │  │  logo.png
  │  └─css
  │          base.css
  │          main.styl
  ├─components
  │  │  HelloWorld.vue
  │  └─base
  │          Button.vue
  │          index.ts
  │          Select.vue
  ├─directive
  │      focus.ts
  │      index.ts
  │      pin.ts
  ├─router
  │      index.ts
  ├─store
  │      index.ts
  ├─utils
  │  │  cookie.ts
  │  │  deep-clone.ts
  │  │  index.ts
  │  │  storage.ts
  │  └─validate
  │          date.ts
  │          email.ts
  │          mobile.ts
  │          number.ts
  │          system.ts
  └─views
  │  About.vue
  │  Home.vue
  │  LuckDraw.vue
  │  TodoList.vue
  └─address
  AddressEdit.tsx
  AddressList.tsx

值得注意的新特性
Vue 3 中一些需要关注的新功能包括：

组合式 API
Teleport
片段
触发组件选项
来自 @vue/runtime-core 的 createRenderer API，用于创建自定义渲染器
单文件组件组合式 API 语法糖 (<script setup>)
单文件组件状态驱动的 CSS 变量 (<style> 中的 v-bind)
SFC <style scoped> 现在可以包含全局规则或只针对插槽内容的规则
Suspense 实验性
#非兼容的变更
下面列出了从 2.x 开始的非兼容的变更：

#全局 API
全局 Vue API 已更改为使用应用程序实例
全局和内部 API 已经被重构为支持 tree-shake
#模板指令
组件上 v-model 用法已更改，以替换 v-bind.sync
<template v-for> 和非 v-for 节点上的 key 用法已更改
在同一元素上使用的 v-if 和 v-for 优先级已更改
v-bind="object" 现在排序敏感
v-on:event.native 修饰符已移除
v-for 中的 ref 不再注册 ref 数组
#组件
只能使用普通函数创建函数式组件
functional attribute 在单文件组件 (SFC) 的 <template> 和 functional 组件选项中被废弃
异步组件现在需要使用 defineAsyncComponent 方法来创建
组件事件现在需要在 emits 选项中声明
#渲染函数
渲染函数 API 更改
$scopedSlots property 已移除，所有插槽都通过 $slots 作为函数暴露
$listeners 被移除或整合到 $attrs
$attrs 现在包含 class 和 style attribute
#自定义元素
自定义元素检测现在在模板编译时执行
特殊的 is prop 的使用被严格限制在被保留的 <component> 标签中
#其他小改变
destroyed 生命周期选项被重命名为 unmounted
beforeDestroy 生命周期选项被重命名为 beforeUnmount
default prop 工厂函数不再可以访问 this 上下文
自定义指令的 API 已更改为与组件生命周期一致，且 binding.expression 已移除
data 选项应始终被声明为一个函数
来自 mixin 的 data 选项现在为浅合并
Attribute 强制策略已更改
一些过渡的 class 被重命名
<TransitionGroup> 不再默认渲染包裹元素
当侦听一个数组时，只有当数组被替换时，回调才会触发，如果需要在变更时触发，则必须指定 deep 选项
没有特殊指令的标记 (v-if/else-if/else、v-for 或 v-slot) 的 <template> 现在被视为普通元素，并将渲染为原生的 <template> 元素，而不是渲染其内部内容。
已挂载的应用不会取代它所挂载的元素
生命周期的 hook: 事件前缀改为 vnode-
#被移除的 API
keyCode 作为 v-on 修饰符的支持
$on、$off 和 $once 实例方法
过滤器 (filter)
内联模板 attribute
$children 实例 property
propsData 选项
$destroy 实例方法。用户不应再手动管理单个 Vue 组件的生命周期。
全局函数 set 和 delete 以及实例方法 $set 和 $delete。基于代理的变化检测已经不再需要它们了。