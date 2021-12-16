### 通过prototype，这个非常方便。Vue.prototype[method]=method;
挂载在原型上
缺点是调用这个方法的时候没有提示
* 调用方式: 直接this.$xxx方法名就可以了
```javascript
Object.keys(tools).forEach(key => {
      Vue.prototype[key] = tools[key]
 })
```
### 通过插件Vue.use(plugin)；
vue.use的实现没有挂载的功能，只是触发了插件的install方法，本质还是使用了vue.prototype

### 通过mixin，Vue.mixin(mixins);
* 调用方式: 直接this.$xxx方法名就可以了
```javascript
Vue.mixin(mixin)
new Vue({
store,
router,
render: h => h(App),
}).$mount('#app')
```
