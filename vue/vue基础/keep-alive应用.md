### keep-alive是什么
keep-alive是一个抽象组件：它自身不会渲染一个DOM元素，也不会出现在父组件链中；

**使用keep-alive包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们。**

一个场景
用户在某个列表页面选择筛选条件过滤出一份数据列表，由列表页面进入数据详情页面，再返回该列表页面，
我们希望：列表页面可以保留用户的筛选（或选中）状态。
keep-alive就是用来解决这种场景。当然keep-alive不仅仅是能够保存页面/组件的状态这么简单，
它还可以避免组件反复创建和渲染，有效提升系统性能。总的来说，keep-alive用于保存组件的渲染状态。

### keep-alive 使用场景和原理
keep-alive 是 Vue 内置的一个组件，可以实现组件缓存，当组件切换时不会对当前组件进行卸载。
常用的两个属性 include/exclude，允许组件有条件的进行缓存。
两个生命周期 activated/deactivated，用来得知当前组件是否处于活跃状态。
keep-alive 的中还运用了 LRU(最近最少使用) 算法，选择最近最久未使用的组件予以淘汰。
Vue.extend 作用和原理
官方解释：Vue.extend 使用基础 Vue 构造器，创建一个“子类”。参数是一个包含组件选项的对象。
其实就是一个子类构造器 是 Vue 组件的核心 api 实现思路就是使用原型继承的方法返回了 Vue 的子类
并且利用 mergeOptions 把传入组件的 options 和父类的 options 进行了合并

### 用法
include定义缓存白名单，keep-alive会缓存命中的组件；
exclude定义缓存黑名单，被命中的组件将不会被缓存；
max定义缓存组件上限，超出上限使用LRU的策略置换缓存数据。
其中 exclude 的优先级比 include 高；
对应两个钩子函数activated 和 deactivated ，
当组件被激活时，触发钩子函数 activated，
当组件被移除时，触发钩子函数 deactivated
组件
```vuex
<keep-alive :include="whiteList" :exclude="blackList" :max="amount">
<component :is="currentComponent"></component>
</keep-alive>
```
路由
```vuex
<keep-alive :include="whiteList" :exclude="blackList" :max="amount">
    <router-view></router-view>
</keep-alive>
```
