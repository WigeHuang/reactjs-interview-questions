### 数组更新检测

这是vue的核心之一， 订阅者模式里面的广播， 还一块就是订阅者的收集(通过notify来通知订阅者做处理)， vue利用defineProperty, 把这两件事做了
del里面我还真忘了， 这几天没事再看看源码，

#### 变更方法

Vue 将被侦听的数组的变更方法进行了包裹，所以它们也将会触发视图更新。这些被包裹过的方法包括：

    push()
    pop()
    shift()
    unshift()
    splice()
    sort()
    reverse()

### 替换数组
变更方法，顾名思义，会变更调用了这些方法的原始数组。相比之下，也有非变更方法，例如 filter()、concat() 和 slice()。它们不会变更原始数组，而总是返回一个新数组。当使用非变更方法时，可以用新数组替换旧数组：

    example1.items = example1.items.filter(function (item) {
    return item.message.match(/Foo/)
    })

你可能认为这将导致 Vue 丢弃现有 DOM 并重新渲染整个列表。幸运的是，事实并非如此。Vue 为了使得 DOM 元素得到最大范围的重用而实现了一些智能的启发式方法，所以用一个含有相同元素的数组去替换原来的数组是非常高效的操作。