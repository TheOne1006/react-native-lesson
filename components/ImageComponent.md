## Image 组件

React Native 的 Image 组件调用的突变的途径比较多,
例如网络图片, 本地磁盘,照相机的图片等.

### Image 组件介绍

Image 目前支持的属性如下:

1. resizeMode: 图片的适应模式
    * 枚举类型: cover, contain, stertch
2. source: 图片的引用地址
    * 值为 `{uri: string}`
3. defaultSource: IOS 支持的属性, 默认的图片地址.如果网络图片加载完成,将取代 defaultSource
4. onLoad: IOS 支持的属性,加载成功时, 触发该事件
5. onLoadEnd: IOS 支持的属性, 不管是加载成功还是失败, 都会触发该事件
6. onLoadStart: IOS 支持的属性, 加载开始时触发该事件
7. onProgress: IOS 支持属性, 加载过程的进度事件
