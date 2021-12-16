### v-model只不过是一个语法糖而已,真正的实现靠的还是

* v-bind:绑定响应式数据

* 触发 input 事件 并传递数据 (核心和重点)

  v-model是默认使用组件的value prop和input事件
  因为V-model并不仅限于Form表单, 目前还支持更改事件名称和变量名称
  model: {
  prop: 'checked',
  event: 'change'
  }