# Taro
### @1.0.7
1. 更改文件后依然存在大量缓存，`ctrl+c`关闭再重启后，可能出现其他错误，需要再重启
2. 直接判断元素是否显示会出现样式加载不了的情况，需要在判断层面加上`<View></View>`
```js
bad
{leader && <View className="tag">团长</View>}

good

{leader && <View>
  <View className="avatar-tag">团长</View> 
</View>}
```
