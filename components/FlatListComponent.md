## FlatList 组件

高性能的简单列表组件，支持下面这些常用的功能：

* 完全跨平台。
* 支持水平布局模式。
* 行组件显示或隐藏时可配置回调事件。
* 支持单独的头部组件。
* 支持单独的尾部组件。
* 支持自定义行间分隔线。
* 支持下拉刷新。
* 支持上拉加载

> Example

```jsx
<FlatList
  data={[{key: 'a'}, {key: 'b'}]}
  renderItem={({item}) => <Text>{item.key}</Text>}
/>
```

本组件实质是基于 `<VirtualizedList>` 组件的封装，因此也有下面这些需要注意的事项：

* 当某行滑出渲染区域之外后，其内部状态将不会保留。请确保你在行组件以外的地方保留了数据。
* 为了优化内存占用同时保持滑动的流畅，列表内容会在屏幕外异步绘制。这意味着如果用户滑动的速度超过渲染的速度，则会先看到空白的内容。这是为了优化不得不作出的妥协，而我们也在设法持续改进。
* 本组件继承自PureComponent而非通常的Component，这意味着如果其props在浅比较中是相等的，则不会重新渲染。所以请先检查你的renderItem函数所依赖的props数据（包括data属性以及可能用到的父组件的state），如果是一个引用类型（Object或者数组都是引用类型），则需要先修改其引用地址（比如先复制到一个新的Object或者数组中），然后再修改其值，否则界面很可能不会刷新。（译注：这一段不了解的朋友建议先学习下js中的基本类型和引用类型。）
* 默认情况下每行都需要提供一个不重复的key属性。你也可以提供一个keyExtractor函数来生成key。

### Props

1. ItemSeparatorComponent?: ?ReactClass<any>
    * 每个项目间隔的 Component
    * 但不存在顶部和底部
2. ListFooterComponent?: ?ReactClass<any>
    * 底部 Component
3. ListHeaderComponent?: ?ReactClass<any>
    * 顶部 Component
4. columnWrapperStyle?: StyleObj
    * 如果设置了多列布局（即将numColumns值设为大于1的整数），则可以额外指定此样式作用在每行容器上。
5. data: ?Array<ItemT>
    * 简化起见, data 目前只支持普通 Array, 如果需要使用其他特殊数据结构，例如immutable数组，请直接使用更底层的VirtualizedList组件。
6. getItem?:
7. getItemCount?:
8. getItemLayout?: (data: ?Array<ItemT>, index: number) => ({length: number, offset: number, index: number})
    * getItemLayout是一个可选的优化，用于避免动态测量内容尺寸的开销，不过前提是你可以提前知道内容的高度。如果你的行高是固定的，getItemLayout用起来就既高效又简单，类似下面这样：
    * getItemLayout={(data, index) => ( {length: 行高, offset: 行高 * index, index} )}
    * 注意如果你指定了SeparatorComponent，请把分隔线的尺寸也考虑到offset的计算之中。
9. horizontal?: ?boolean
    * 设置为true则变为水平布局模式。
10. keyExtractor: (item: ItemT, index: number) => string
    * 此函数用于为给定的item生成一个不重复的key。
    * Key的作用是使React能够区分同类元素的不同个体，以便在刷新时能够确定其变化的位置，减少重新渲染的开销。
    * 若不指定此函数，则默认抽取item.key作为key值。
    * 若item.key也不存在，则使用数组下标。
11. legacyImplementation?:  ?boolean
    * 设置为true则使用旧的ListView的实现。
12. numColumns: number
    * 多列布局只能在非水平模式下使用。此时组件内元素会从左到右从上到下按Z字形排列，类似启用了flexWrap的布局。组件内元素必须是等高的——暂时还无法支持瀑布流布局。
13. onEndReached?: ?(info: {distanceFromEnd: number}) => void
    * 当所有的数据都已经渲染过，并且列表被滚动到距离最底部不足onEndReachedThreshold个像素的距离时调用。
14. onEndReachedThreshold?:  ?number
15. onRefresh?: ?() => void
16. onViewableItemsChanged?:  ?(info: {viewableItems: Array<ViewToken>, changed: Array<ViewToken>}) => void
17. ...

### Methods

1. scrollToEnd(params?: object)
    * 滚动到底部。如果不设置getItemLayout属性的话，可能会比较卡。
2. scrollToIndex(params: object)
    * 根据索引,滚动到指定项目。如果不设置getItemLayout属性的话，可能会比较卡。
3. scrollToItem(params: object)
    * 根据项目,滚动到指定项目。如果不设置getItemLayout属性的话，可能会比较卡。
4. scrollToOffset(params: object)
    * 滚动到指定高度。如果不设置getItemLayout属性的话，可能会比较卡。
5. recordInteraction()
    *
