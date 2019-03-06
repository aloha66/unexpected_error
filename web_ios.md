# css
1. 去除表单等元素的底色`-webkit-tap-highlight-color: rgba(0,0,0,0);`
2. 防止把整个webview跟随触点一起滑动，应该保持固定
```
html,
body {
  position: fixed;
  left: 0;
  top: 0;
  bottom: 0;
  right: 0;
  overflow: auto;
}
```
3.解决ios滑动不流畅`-webkit-overflow-scrolling:touch;`


## 有赞
### vant@1.5.1
1. 当下拉刷新组件包含popup组件时，popup的高度固定为内容高度，解决方案
 ```
 .van-pull-refresh__head + div {
    min-height: 100vh
}
 ```


# js
1. 当输入文字的时候，`input`、'textarea'会下沉，，需要在`focus`和`input`的时候处理，在`blur`释放处理结果。解决方案有两个

        1.1 使用scrollTop
        当在focus和input状态持续模拟上滑而且滑动距离足够大的时候，就可以保持input框在视野范围内。实测发现微信浏览器使用scrollTo报错
  
        1.2 使用scrollIntoView
        document.querySelector('textarea').scrollIntoView()简单使用即可。
  上述方案，需要加入`setInterval`持续执行，单次的`setTimeout`不一定成功。其次发现一台iPhone7 ios11对这两种解决方案无效。

2.解决ios和安卓必须输入数字，限制长度（安卓没有问题,ios所有字符都能输），`type="number"`导致maxlength失效。
```
<input v-model="age" type="number" pattern="[0-9]*">
// type="number" pc和安卓正常表现，ios需要加入pattern="[0-9]*"
由于maxlength失效，正则pattern限制字数无果，还是采用js控制长度
if (value.length > 11) {
          this.phone = value.slice(0, 11);
        }
```

3.关于在vue使用better-scroll的一些问题
 3.1 监听事件例如`scrollEnd`,代码如下：
 ```
 this.scroll.on('scrollEnd', (pos) => {
            console.log(this.maxScrollY,this.scroll.maxScrollY)
          })
 ```
 尽管在调试器中能看到`this.maxScrollY`的值，实际上这时的this是指向vue的而不是函数的，所以会出现问题。使用`this.scroll.maxScrollY`或者改用普通函数能避免问题
  3.2 使用better-scroll，必须在`.wrapper`设置样式`overflow: hidden; height: 100vh;`
 
 
4. 关于使用`Intl.DateTimeFormat`来优化大量格式化日期，ios10以下不支持，polyfill无果。
5.`date.toLocaleString`在ios10以下的表现不如其他平台，需单独处理




# 微信端（X5）
1. 使用js-cookie,设置cookie，默认有效时间是session，甚至时间默认有点怪异，建议手动添加一个到期时间。在PC端，默认有效时间是永久。
