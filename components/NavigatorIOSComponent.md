## NavigatorIOS 组件

应用程序往往由很多视图组件组成. 就像 Web App 一样, 单页应用也会存在不同的路由.

因此,一个应用最为重要的功能之一就是 **"路由"** (或者叫 导航).

因为只有存在路由,才能实现视图之间的 _切换_ 和 _前进_, _后退_.

在 React Native 中,就存在一个专门方便让我们进行路由管理.

React Native 也提供了一个兄弟组件, 那就是 `Navigator`

### NavigatorIOS 介绍

该组件本质上是对 `UIKit navigation` 的包装.
路由是一个 JavaScript 对象,代表着一个页面(视图)组件.
NavigatorIOS 组件默认的路由提供了 initialRoute 属性. 实例代码如下:

```js
render () {
    return(
        <NavigatorIOS
            initialRoute={{
                component: MyView,
                title: 'My View Title',
                passProps: { myProp: 'foo' },
            }}
        >
    )
}
```

### NavigatorIOS 组件属性

1. barTintColor
    * 导航条的背景颜色
2. initialRoute: Object
    * 初始化路由对象
3. itemWrapperStyle: ?
    * 为每一项定制样式, 例如设置每个页面的背景颜色
4. navigationBarHidden: Bollean
    * 为 ture 是,隐藏导航栏
5. shadowHidden: Bollean
    * 是否隐藏阴影
6. tintColor: ?
    * 导航栏上按钮的颜色设置
7. titleTextColor: ?
    * 导航栏上字体的颜色
8. translucent: Bollean
    * 导航栏是否半透明

在组件视图切换的时候, navigator 会作为一个属性对象被传递.

我们可以通过 `this.props.navigator` 获取 navigator 对象.
navigator 是一个十分重要的对象.它可以孔子路由的跳转和组价的加载.

> NavigatorIOS initialRoute 可配置属性

1. component: Class
    * 该页面需要加载的组件视图
2. title: String
    * 需要在头部显示的标题
3. passProps: Object
    * 用于页面间的数据传递
4. backButtonIcon: Image.propTypes.source
    * 后退按钮图标
5. backButtonTitle: String
    * 后退按钮标题
6. leftButtonIcon: Image.propTypes.source
    * 左边按钮图标
7. leftButtonTitle: String
    * 左侧按钮标题
8. onLeftButtonPress: function
    * 左侧按钮点击事件
9. rightButtonIcon: Image.propTypes.source
    * 右侧按钮图标
10. rightButtonTitle: string
    * 右侧按钮标题
11. onRightButtonPress: function
    * 右侧按钮点击事件
12. wrapperStyle: Object
    * 包裹样式

> navigator 对象

1. push(route)
    * 加载一个新的页面(视图/路由) 并且路由到该页面
2. pop()
    * 返回到上一个页面
3. popN(n)
    * 一次性返回 N 个页面, 当 N = 1, 即相当与 pop() 方法的效果
4. replace(route)
    * 替换当前路由
5. replacePrevous(route)
    * 替换前一个页面的视图并且退回过去
6. resetTo(route)
    * 取代最顶层的路由并退回过去.
7. popToTop()
    * 回到最上层视图







- - -
