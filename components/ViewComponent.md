## View 组件

### 介绍

`View` 是一个容器组件, 提供了视图布局功能, 是 UI 组件中最基本的组件.
他可以 **多层嵌套**, 支持 flexbox 布局.起到 __容器组件__ 的作用.


### 其他

```js
import { AppRegistry, StyleSheet, PixelRatio } from 'react-native'
```

1. AppRegistry 负责注册 App 的入口组件
2. StyleSheet 创建样式表.
3. PixelRatio API
    - PixelRatio.get() 方法用于高清设备的像素比. 使用 1/PixelRatio.get() 可以获取最小线宽.
