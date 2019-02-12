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

## vue

a使用proxy处理跨域请求地址必须是相对路径，否则跨域失效
```
// bad
axios.get("http://localhost:4000/test");

// good
axios.get("/test");

```
