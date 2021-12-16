出现该问题是因为在 Vue 代码尚未被解析之前，尚无法控制页面中 DOM 的显示，
所以会看见模板字符串等代码。解决方案是，
在 css 代码中添加 v-cloak 规则，同时在待编译的标签上添加 v-cloak 属性：

```vue
[v-cloak] { display: none; }

<div v-cloak>

{{ message }}

</div>
```

