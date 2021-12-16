### Vue 中异常处理包含以下几个方面的技巧：

* errorHandler
* warnHandler
* renderError
* errorCaptured
* window.onerror (不仅仅针对 Vue)

### 技巧 1：errorHandler

我们要学习的第一个技巧是errorHandler。你也许知道，这是 Vue 中最广泛使用的异常处理方式。

```vue
Vue.config.errorHandler = function(err, vm, info) {};

err指代 error 对象
info是一个 Vue 特有的字符串，
vm指代 Vue 应用本身。
记住在一个页面你可以有多个 Vue 应用。这个 error handler 作用到所有的应用。

```vue
Vue.config.errorHandler = function(err, vm, info) {
console.log(`Error: ${err.toString()}\nInfo: ${info}`);
};
```

第一种错误不会触发 errorHandler，它只是一个 warning。

第二种错误会抛出错误被 errorHandler 捕获：

Error: ReferenceError: x is not defined Info: render 第三种错误也会被捕获：

Error: ReferenceError: x is not defined Info: v-on handler 记住info里面的信息也是非常有用的。

### 技巧 2: warnHandler

warnHandler用来捕获 Vue warning。记住在生产环境是不起作用的。

Vue.config.warnHandler = function(msg, vm, trace) {}; msg和vm都容易理解，trace代表了组件树。请看下面的例子：

```vue
Vue.config.warnHandler = function(msg, vm, trace) {
console.log(`Warn: ${msg}\nTrace: ${trace}`);
};
```

第一个错误被warnHandler捕获：

Warn: Property or method 'name' is not defined on the instance but referenced during render. Make sure that this
property is reactive, either in the data option, or for class-based components, by initializing the property.
See: https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties. Trace:

### 技巧 3: renderError

和前面两个不同，这个技巧不适用于全局，和组件相关。并且只适用于非生产环境。

下面是一个简单的例子：

```vue
const app = new Vue({
el: "#app",
renderError(h, err) {
return h("pre", { style: { color: "red" } }, err.stack);
}
});
```

第一个例子是没有效果的，因为只是一个warning。第二个例子就会在网页上显示具体的错误信息

老实说，我没觉得这个比直接看控制台好多少。但是，如果你们的 QA 团队或则测试对浏览器控制台不熟悉的话，这个还是蛮有用的。

### 技巧 4: errorCaptured

errorCaptured是最后一个和 Vue 相关的技巧，文档是这么介绍的：

当捕获一个来自子孙组件的错误时被调用。此钩子会收到三个参数：错误对象、发生错误的组件实例以及一个包含错误来源信息的字符串。此钩子可以返回 false 以阻止该错误继续向上传播。

基于我的一些分析，这个 error Handler 只能在父组件中处理子组件的错误。据我所知，我们没法直接在 Vue 的主实例(main instance)中使用它。

为了测试，我构造了下面的例子：

```vue
Vue.component("cat", {
template: `
<div><h1>Cat: </h1>
<slot></slot>
</div>`,
props: {
name: {
required: true,
type: String
}
},
errorCaptured(err, vm, info) {
console.log(`cat EC: ${err.toString()}\ninfo: ${info}`);
return false;
}
});

Vue.component("kitten", {
template: "
<div><h1>Kitten: {{ dontexist() }}</h1></div>",
props: {
name: {
required: true,
type: String
}
}
});
```

注意 kitten 组件的代码是有 BUG 的。

<div id="app" v-cloak>
    <cat name="my cat">
        <kitten></kitten>
    </cat>
</div>
捕获的信息如下:

cat EC: TypeError: dontexist is not a function info: render 下面是运行实例。

errorCaptured是个很有趣的特性，我想那些构建组件库的开发者应该会用到吧。这个特性更像是面向组件开发者而不是一般开发者。

### 终极技巧: window.onerror

最后也是最重要的一个候选项 window.onerror。它是一个全局的异常处理函数，可以抓取所有的 JavaScript 异常。

window.onerror = function(message, source, line, column, error) {}; 我想函数的参数中只有source难以从字面上理解吧，它代表了当前的 URL。

接下来事情就比较好玩了。如果你定义了onerror，但是没有启用Vue.config.errorHandler，那么有很多异常都抓不到。Vue 希望你定义它，否则异常不会抛出去的。这到底有没有意义？我不是很懂，我觉得没必要，甚至有点奇怪。

如果定义errorHandler的代码有 BUG，那么运行起来也不会被onerror抓到。下面的例子中，如果将oopsIDidItAgain()解注释，你就会发现这个问题。只有第二个按钮没有和 Vue
绑定，所以报错无论如何都会被抓到。运行实例