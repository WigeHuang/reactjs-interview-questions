### 组件是什么
小型的、独立的、可复用的UI模块

Vue组件 = Vue实例 = new Vue(options);

### 组件的组成
属性、事件、插槽
#### 属性
 * 自定义属性 props 组件props中声明的属性
 * 原生属性 attrs 没有声明的属性，默认自动挂载在根元素上，设置inheritAttrs为false关闭自动挂载
 * 特殊属性 class、style 挂载到组件根元素上、支持字符串、对象、数组等多种语法
#### 事件
 * 普通事件 @click @ input @change @xxx 等事件，通过this.$emit('xxx',...')触发
 * 修饰符事件 @input.trim,@click.stop,@submit.pervent 等，一搬用于原生HTML元素
#### 插槽
 * 普通插槽  <template slot='xxx'></template><template v-slot:xxx></template>
 * 作用域插槽 <template slot='xxx' slot-scope='props'></template><template v-slot:xxx='props'></template>
 * 2.6版本之后不分类了

### 总结
事件和插槽也可以归类为属性，都是父组件传给子组件的元素
都可以通过传递属性来实现