## TouchableComponent 类组件

React Native 没有像 Web 开发那样可以给元素绑定 click 事件.

为了像 Text 组件那样使得其他组件可以被点击. React Native 提供了3个组件来做这件事情.

这三个组件称为 "Touchable类组件",

1. TouchableHighlight: 触摸高亮,用户点击,会产生高亮效果
2. TouchableOpacity: 触摸透明,用户点击, 点击的组件会出现透明过度效果
3.  TouchableWithoutFeedback: 无反馈性触摸, 用户点击时, 点击的组件不会出现任何视觉变化

### TouchableHightLight

属性如下:

1. activeOpacity: 触摸时透明度设置
2. onHideUnderlay: 隐藏背景阴影时触发该事件
3. onShowUnderlay: 出现背景阴影时触发该事件
4. underlayColor: 点击背景阴影效果的背景颜色
