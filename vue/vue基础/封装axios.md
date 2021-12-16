ajax：最原始的后端请求技术，new XMLHttpRequest()创建xhr对象，用setRequestHeader()设置请求头、send发送请求等。。
axios：写法axios().then().catch()，基于XMLHttpRequest封装的Promise实现版本，区别有从 node.js 创建 http 请求等
fetch：fetch().then().then().catch()，基于原生js，没有使用XMLHttpRequest对象
