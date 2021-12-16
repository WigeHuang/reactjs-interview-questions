虚拟列表：vue-virtual-scroll-list，vue-virtual-scroller……
冻结属性，让不必要的属性不响应：Object.freeze, 
或者使用 Object.defineProperty 将对象属性的configurable设置为false，
源码：vue/src/core/observer/index.js

----------分页不是更好。。。