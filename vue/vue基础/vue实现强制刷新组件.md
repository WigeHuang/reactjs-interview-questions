强制重新渲染
this.$forceUpdate()

强制重新刷新某组件
```vuex
//模版上绑定key
<SomeComponent :key="theKey"/>
//选项里绑定data
data(){
    return{
    theKey:0
    }
}
```

//刷新key达到刷新组件的目的
theKey++;