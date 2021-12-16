项目中很多情况下都需要进行路由之间的传值，想过很多种方式
sessionstorage/localstorage/cookie 进行离线缓存存储也可以，用vuex也可以，不过有些大材小用吧，不管怎么说因场景而异
下面我来说下vue自带的路由传参的三种基本方式
### 路由跳转
router-view 实现路由内容的地方，引入组件时写到需要引入的地方
需要注意的是，使用vue-router控制路由则必须router-view作为容器。
通过路由跳转的三种方式
* router-link 【实现跳转最简单的方法】 <router-link to='需要跳转到的页面的路径> 底层是a标签
* this.$router.push({ path:’/user’}) 常用于路由传参
* this.$router.replace{path：‘/’ }
### 页面刷新参数不丢失
```vue
methods：{
  insurance(id) {
   //直接调用$router.push 实现携带参数的跳转
    this.$router.push({
      path: `/particulars/${id}`,
    })
}
路由配置：
{
    path: '/particulars/:id',
    name: 'particulars',
    component: particulars
}
页面获取：
this.$route.params.id

```
### 通过params来传递参数
通过路由属性中的name来确定匹配的路由，通过params来传递参数。
```vue
methods：{
  insurance(id) {
       this.$router.push({
          name: 'particulars',
          params: {
            id: id
          }
        })
  }
```
### 使用path来匹配路由
使用path来匹配路由，然后通过query来传递参数
这种情况下 query传递的参数会显示在url后面?id=？
```vue
methods：{
  insurance(id) {
        this.$router.push({
          path: '/particulars',
          query: {
            id: id
          }
        })
  }
```