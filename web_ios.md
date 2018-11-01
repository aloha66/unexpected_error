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



# js
1. 当输入文字的时候，`input`、'textarea'会下沉，，需要在`focus`和`input`的时候处理，在`blur`释放处理结果。解决方案有两个

        1.1 使用scrollTop
        当在focus和input状态持续模拟上滑而且滑动距离足够大的时候，就可以保持input框在视野范围内。实测发现微信浏览器使用scrollTo报错
  
        1.2 使用scrollIntoView
        document.querySelector('textarea').scrollIntoView()简单使用即可。
  上述方案，需要加入`setInterval`持续执行，单次的`setTimeout`不一定成功。其次发现一台iPhone7 ios11对这两种解决方案无效。
