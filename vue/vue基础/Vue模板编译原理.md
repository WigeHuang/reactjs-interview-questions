vue 在进行差值处理 和双向绑定时用了Mustache模板引擎

Vue 的编译过程就是将 template 转化为 render 函数的过程 分为以下三步

* 第一步是将 模板字符串 转换成 element ASTs（解析器）

* 第二步是对 AST 进行静态节点标记，主要用来做虚拟DOM的渲染优化（优化器）

* 第三步是 使用 element ASTs 生成 render 函数代码字符串（代码生成器）

（1）parse 根据正则进行字符串解析，得到指令、class、style等数据，形成语法树（AST）

（2）对 parse 生成的 AST 进行静态内容的优化，标记静态节点（和数据没有关系不需要每次都刷新的内容），标记静态根节点。

（3）generate 生成 render

生成render 的 generate 函数的输入也是 AST，它递归了 AST 树，为不同的 AST 节点创建了不同的内部调用方法，等待后面的调用

