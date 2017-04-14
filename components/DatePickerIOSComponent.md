## DatePickerIOS 日期选择 for IOS

使用 `DatePickerIOS` 来在iOS平台上渲染一个日期/时间选择器。

这是一个受约束的(Controlled)组件, 所以你必须监听onDateChange回调函数并且及时更新date属性来使得组件更新，
否则用户的修改会立刻被撤销来确保当前显示值和props.date一致。


### Props

1. date: Date
    * 当前选择的日期
2. maximumDate?: Date
    * 最大日期
    * 限制可能的日期/时间值的范围。
3. minimumDate?: Date
    * 最小日期
    * 限制可能的日期/时间值的范围。
4. minuteInterval?: enum(1, 2, 3, 4, 5, 6, 10, 12, 15, 20, 30)
    * 选择分钟间隔
5. mode?: enum('date', 'time', 'datetime')
    * 日期选择器模式
6. onDateChange: function
    * 时间更改方法
    * 当用户修改日期或时间时调用此回调函数。
    * 唯一的参数是一个日期对象，表示新的日期和时间。
7. timeZoneOffsetInMinutes?: number
    * 默认情况下，选择器会选择设备的默认时区。通过此参数，可以指定一个时区。
    * 举个例子，要使用北京时间（东八区），可以传递8 * 60。


> 布局时小心:

确保样式被修改

```jsx
<View style={{alignSelf: 'stretch'}}>
            <DatePickerIOS
                date={this.state.date}
                mode="date"
                timeZoneOffsetInMinutes={this.state.timeZoneOffsetInHours * 60}
                onDateChange={this.onDateChange}
                />
</View>
```
