# css
预设css
`i,em {
  font-style: normal;
}
h1,h2,h3,h4,h5 {
  font-weight: normal;
}
ul {
  list-style: none
}
pre {
  margin: 0;
  font-family: inherit;
  font-size: inherit;
  white-space: pre-wrap;
  word-break: normal;
}`

# js
1. 在用axios进行OAuth2认证传参的时候，必须引入qs库进行序列化
2. `robust-websocket`一个包含心跳检测、重连的库，简单易用
3. 数据库返回的时间若相差8小时，前端用`new Date(time)`解决

## vue

1. 使用proxy处理跨域请求地址必须是相对路径，否则跨域失效
```
// bad
axios.get("http://localhost:4000/test");

// good
axios.get("/test");

```
2. cli3.3
```
new HtmlWebpackPlugin({
  template: "public/index.html",
  }
  指定template后，BASE_URL失效？？？ 删除或重新指定即可
```
3. ivivew 3.3.3

按需加载时候，像`Message`之类的组件需要绑定到Vue的原型`Vue.prototype.$Message = Message`
