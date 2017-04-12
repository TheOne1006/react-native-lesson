## TabBarIOSComponent 组件

React Native 提供 Tab 功能:

TabBarIOS 组件的属性比较少,主要有3个:

1. barTintColor: Tab 栏的背景颜色
2. tintColor: 选中某个 Tab, 该 Tab 图标颜色
3. translucent: Tab栏是否透明

TabBarIOS.Item 组件是 TabBarIOS 组件的某一项 Tab, 支持如下属性:

1. badge: 红色的提示数字, 可以用作消息提醒
2. icon: Tab图标,如果不指定, 默认显示系统图标
3. onPress: 点击事件, 当某个 Tab 被选中时,需要改变组件的 `selectd={true}` 设置
4. selected: 是否选中某个 Tab, 如果其值为 true, 则选中病显示子组件
5. selectedIcon: 选中状态的图标, 如果为空, 则将图标变成蓝色
6. systemIcon: 系统图标, 其值为枚举类型
    * bookmarks, contacts, downloads, favorites, featured
    * history, more, most-recent, most-viewed, recents
7. title: 标题,他会出现在图标底部
