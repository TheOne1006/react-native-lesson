## ActivityIndicator

显示一个圆形的loading提示符号

### Props

1. animating?: bool
    * 是否要显示指示器，
    * 默认为true，表示显示。
2. color?: [object Object]
    * 滚轮的前景颜色（默认为灰色）
3. size?: [object Object], [object Object]
    * 指示器的大小。small的高度为20，large为36。
    * 只有在 Android 才支持数字
4. hidesWhenStopped?: bool
    * 在没有动画的时候，是否要隐藏指示器（默认为true）。
    * 仅 IOS
