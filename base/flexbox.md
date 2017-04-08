## flexbox 布局

flexbox 是 React Native 应用开发中比不可少.

### 布局模型

flexbox布局由 *伸缩容器* 和 *伸缩项目* 组成,
任何一个元素都可以指定为 flexbox 布局,
其中设为 `display: flex` 或者 `display: inline-flex` 元素成为 __伸缩容器__.

伸缩容器的子元素成为 __伸缩项目__, 伸缩项目使用伸缩布局模型来排版.


默认情况, 伸缩容器由两根轴组成,即 主轴(main axis) 和交叉轴(cross axis).

其中主轴开始的位置叫做 main start, 结束位置叫做 main end.

交叉轴开始位置叫做 cross start, 借宿位置叫做 cross end.

伸缩项目在主轴上占据的空间叫做 main size, 在交叉轴上占据的空间叫做 coress size.

### 伸缩容器属性

> Note: flexbox 时, CSS 的 columns 在伸缩容器上没有效果.
>       float, clear 和 vertical-align 在伸缩项目上没有效果.

1. display
    - 指定元素是否为伸缩容器
    - 值: flex| inline-flex
2. flex-direction
    - 指定主轴的方向
    - 值: row (defualt)| row-reverse | column | column-reverse
    - row: 伸缩容器为水平方向, 伸缩项目排版从左到右 => `[ 1, 2, 3]`
    - row-reverse: 伸缩容器为水平方向, 伸缩项目排版从右到左 => `[3,2,1]`
    - column: 伸缩容器为垂直方向, 伸缩项目的排版为从上到下
    - column-reverse: 伸缩容器为垂直方向, 伸缩项目排版从下到上
3. flex-wrap
    - 指定伸缩容器的 __主轴线方向空间不足__ 情况下, _是否换行_ 以及 _如何换行_.
    - 值: nowrap (default) | wrap | wrap-reverse
    - nowrap: 即使空间不足,伸缩容器也不允许换行. => `[1,2,3,4,5]`
    - wrap: 伸缩容器在空间不足情况下允许换行, 若主轴为水平轴, 则换行的方向为从上到下.
        -  `[1,2,3]`
        -  `[4, 5]`
    - wrap-reverse: 伸缩容器不足情况下允许换行, 若主轴为水平轴, 则换行为从下到上(与 wrap 相反)
        - `[4,5]`
        - `[1,2,3]`
4. flex-flow = flex-direction flex-wrap
    - 该属性是 flex-direction 和 flex-wrap 属性的缩写版本
    - 默认值为 row nowrap
5. justify-content
    - 定义伸缩项目沿主轴线的对齐的方式
    - 值: flex-start (default)| flex-end | center | space-between | space-around
    - flex-start: 伸缩项目向主轴线的起始位置靠齐.
    - flex-end: 伸缩项目向主轴线的结束位置靠齐.
    - center: 伸缩项目向主轴线的中间位置靠齐.
    - space-between: 伸缩项目会平均的分布在主轴线里,两端紧挨终始点
    - space-around: 伸缩项目会平均分配在主轴线里,两端保留一半的空间
6. align-items
    - 定义伸缩项目在容器的交叉轴上的对齐方式
    - 值: flex-start(default) | flex-end | center | baseline | stretch
    - flex-start: 伸缩项目向交叉轴的起始位置靠齐
    - flex-end: 伸缩项目向交叉轴的结束位置靠齐
    - center: 伸缩项目向交叉轴的中心靠齐
    - baseline: 伸缩项目根据他们的基线对齐
    - stretch: 伸缩项目在交叉轴方向上拉伸填充整个伸缩容器(ps: 这个效果,拉伸项目是不能设置高度的)
7. align-content
    - 调整伸缩项目出现换行后再交叉轴上的对齐方式, 类似于伸缩项目在主轴上使用 `justify-content`
    - flex-wrap: wrap 这个属性要开启才能出现换行效果.

### 伸缩项目属性

1. orider: integer
    - 定义项目的排序, 数值越小排序越靠前,
    - integer 默认值为 0
2. flex-grow: number
    - 定义伸缩项目放大比例,
    - 默认为0 : 如果剩余存在空间,也不放大.
    - 1: 每个伸缩项目将设置为一个大小相等的剩余空间.
    - 2: 这个伸缩项目所占的剩余空间是其他项目所占剩余空间的 2 倍
3. flex-shrik: number
    - 设置伸缩项目的收缩能力
    - 默认值为1
4. flex-basis: length | auto ?
    - 伸缩项目的基准值, 剩余空间按比例进行伸缩.
5. flex: none | flex-grow flex-shrink flex-basis
    - 默认值为 0 1 auto
    - 快捷值 auto ( 1 1 auto)
    - none( 0 0 auto)
6. align-slef: auto | flex-start | flex-end | center | baseline | stretch
    - 设置单独的伸缩项目在交叉轴上的对齐方式,会覆写默认的对齐方式
    - auto: 伸缩项目按照自身设置宽高显示,如果没有设置,按照 stretch 来计算.
    - flex-start: 伸缩项目向交叉轴的开始的位置靠齐.
    - flex-end: 伸缩项目向交叉轴的结束位置靠齐.
    - center: 伸缩项目向交叉轴的中心位置靠齐.
    - baseline: 伸缩项目按照基线对齐.
    - stretch: 伸缩项目在交叉轴方向沾满伸缩容器.

### React Native 中使用 flexbox

React Native 引入 flexbox.

React Native 目前主要支持 flexbox 如下布局.

> Note: 全部使用驼峰写法

1. alignItems
    - 值: flex-start | flex-end | center | stretch
2. alignSelf
    - 值: auto | flex-start | flex-end | center | stretch
3. flex
    - 同上
4. flexDirection
    - 同上, React Native 中默认是 column
5. flexWrap
    - wrap | nowrap
6. justifyContent
    - flex-start | flex-end | center | space-between | space-around
