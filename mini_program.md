## Taro
### @1.0.7
1. 更改文件后依然存在大量缓存，`ctrl+c`关闭再重启后，可能出现其他错误，需要再重启



## iview-weapp
### @2.0.0
1. 在grid组件绑定touch事件或者tap事件会报错，[issue](https://github.com/TalkingData/iview-weapp/issues/77),但是在绑定`<i-grid-label>`点击时没报错。
解决方案： 在`<i-grid-icon>`里面追加一个`<view>`在view绑定事件即可避免。


## uni-app 
### @1.8

1. 条件编译：在tabBar的list数组最后一个元素加条件编译会报错

