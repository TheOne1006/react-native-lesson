## Button

一个基本的按钮组件，应该可以在任何平台上呈现。

支持最低级别的定制。

如果默认的 button 不适合你的应用, 你可以使用 TouchableOpacity 或者 TouchableNativeFeedback.
可以查看 Button 源码,或者 <https://js.coach/react-native/react-native-facebook-login?search=button>
查找你想要的 button

> Example

```jsx
<Button
  onPress={onPressLearnMore}
  title="Learn More"
  color="#841584"
  accessibilityLabel="Learn more about this purple button"
/>
```

### Props

1. accessibilityLabel?: ?string
    * 用于给残障人士显示的文本（比如读屏器软件可能会读取这一内容）
2. color?: ?string
    * ios 文字颜色
    * Android 背景颜色
3. disabled?: ?boolean
    * 如果为 true, 禁用此组件的交互
4. onPress: () => any
    * 用户点击按钮时调用处理函数
5. testID?: ?string
    * 用于在端到端测试中查找此视图
6. title: string
    * 显示文本
