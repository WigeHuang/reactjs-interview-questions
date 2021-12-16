### Proxy的优势如下:

* Proxy可以直接监听对象而非属性；

* Proxy可以直接监听数组的变化；

* Proxy有多达 13 种拦截方法,不限于 apply、ownKeys、deleteProperty、has 等等是 Object.defineProperty 不具备的；

* Proxy返回的是一个新对象,我们可以只操作新的对象达到目的,而 Object.defineProperty 只能遍历对象属性直接修改；

* Proxy作为新标准将受到浏览器厂商重点持续的性能优化，也就是传说中的新标准的性能红利；

### Object.defineProperty的优势如下:

兼容性好，支持IE9，而 Proxy 的存在浏览器兼容性问题,
而且无法用 polyfill 磨平，
因此 Vue 的作者才声明需要等到下个大版本( 3.0 )才能用 Proxy 重写。

### Object.defineProperty 理解
Object.defineProperty定义新属性或修改原有的属性；
vue的数据双向绑定的原理就是用的Object.defineProperty这个方法，里面定义了setter和getter方法，
通过观察者模式（发布订阅模式）来监听数据的变化，从而做相应的逻辑处理。
