### 一般有两种模式
* （1）hash 模式： onHashChange()事件
  在浏览器中符号“#”，#以及#后面的字符称之为hash，用window.location.hash读取；
  特点：hash虽然在URL中，但不被包括在HTTP请求中；用来指导浏览器动作，对服务端安全无用，hash不会重加载页面。
   hash 模式下，仅 hash 符号之前的内容会被包含在请求中，如http://www.xxx.com，
   因此对于后端来说，即使没有做到对路由的全覆盖，也不会返回404 错误。
* （2）history 模式：
  history采用HTML5的新特性；且提供了两个新方法：pushState（），replaceState（）可以对浏览器历史记录栈进行修改，
以及popState事件的监听到状态变更。history 模式下，前端的 URL 必须和实际向后端发起请求的 URL 一致，
如http://www.xxx.com/items/id。后端如果缺少对 /items/id 的路由处理，将返回 404 错误。
Vue-Router 官网里如此描述：“不过这种模式要玩好，还需要后台配置支持……所以呢，
你要在服务端增加一个覆盖所有情况的候选资源：如果 URL 匹配不到任何静态资源，则应该返回同一个 index.html 页面，
这个页面就是你 app 依赖的页面。”

### 实际上存在三种模式：
  Hash:      使用URL的hash值来作为路由。支持所有浏览器。url路径会出现“#”号字符
  History:   依赖H5 API和后台配置，没有后台配置的话，页面刷新时会出现404
  整个地址重新加载，可以保存历史记录，方便前进后退
  Abstract： 支持所有javascript运行模式。如果发现没有浏览器的API，路由会自动强制进入这个模式。
  
修改模式：mode: 'history'
```vue
import Vue from 'vue'
import Router from 'vue-router'
import Main from '@/components/Main'
Vue.use(Router)

export default new Router({
  mode: 'history',
  routes: [
    {
      path: '/',
      component: Main
    }
  ]
})
```