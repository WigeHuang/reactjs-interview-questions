this.$nextTick()将回调延迟到下次 DOM 更新循环之后执行。
在修改数据之后立即使用它，然后等待 DOM 更新。
它跟全局方法 Vue.nextTick 一样，不同的是回调的 this 自动绑定到调用它的实例上。

在created()钩子函数执行的时候DOM 其实并未进行任何渲染，而此时进行DOM操作并无作用，
而在created()里使用this.$nextTick()可以等待dom生成以后再来获取dom对象

this.$nextTick()在页面交互，尤其是从后台获取数据后重新生成dom对象之后的操作有很大的优势，
这里只是简单的例子，实际应用中更为好用~

 