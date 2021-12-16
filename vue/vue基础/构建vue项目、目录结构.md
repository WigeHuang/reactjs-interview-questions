### 简单点

安装node.js
安装vue：npm install vue -g
安装webpack：npm install webpack -g
安装vue-cli：npm install vue-cli -g
构建项目： vue init webpack 文件名

* 视图页面放在 pags或者views中
* 静态文件放在static中
* 资源文件放在assets中
* 样式文件放在styles中
* 辅助库放在utils中
* 配置文件可以放在config或者constants中
* vuex的文件放在stores中，至于getters, actions, mutation, modules可以参考vuex的文档
* 路由文件放在routes中
* 所有组件放在components中
* 共享代码也可以使用shared作为目录
* 布局组件可以放在layouts目录中

vue-cli实际上已经很成熟了，目录除了脚手架默认的，
1、一般会额外创建views，components，api，utils，stores等；
2、下载重要插件，比如axios，dayjs（moment太大），其他的会根据项目需求补充；
3、封装axios，统一api调用风格和基本配置；
4、如果有国际化需求，配置国际化；
5、开发，测试和正式环境配置，一般不同环境API接口基础路径会不一样；

### 扩展
#### 持续集成和部署
目前开源项目通常采用Travis，而一般公司内部项目通常采用Jenkins来做持续集成，
在部署上通常采用Docker，集群上使用KubeOperator来管理。
API请求方式 通常采用Restfull的方式来请求数据，也可以采用GraphQL的方式来请求。
如果采用Restfull的方式通常可以使用axios, fetch api。GraphQL可以使用Apollo Client。
#### 项目文档和组件测试文档
  除了在项目根目录放一个README.MD文件外，通常还需要一些比如CHANGELOG.md, PLAD.md等文档，
还有一些组件的使用文档，可以考虑使用styleguide和storybook。

#### GIT版本控制

#### 代理和数据Mock
SPA页面开发通常都是配置代码来调用后端的接口数据，怎么配置可以参考@vue/cli文档。
数据Mock主要用到一个mockjs，至于怎么起服务自行搜索。

#### 项目中用到的库
