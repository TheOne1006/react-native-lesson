## TextInput 组件

TextInput 是可以通过键盘将文本输入到 App 的组件,它提供了比较丰富的功能.
如自动校验, 占位符, 以及制定弹出不同的键盘类型等.

### 介绍

我们可以用 TextInput 组件做基本的组件, 也可以用 TextInput 组件做自动补全的搜索功能.

TextInput 主要属性和事件如下所示:

1. autoCapitalize: 当用户输入时,用于提示,
    * 枚举类型: 'none', 'sentences', 'words', 'characters'
2. placeholder: 占位符
    * String
3. value: 文本输入框的默认值
    * String
4. placeholderTextColor: 占位符文本的颜色
5. password: 密码输入框
    * 如果为 true, 则是密码输入框, 文本显示为 "*"
6. multiline: 多行输入
    * Bollean
7. editable: 文件是否可编辑, 默认 true
    * Bollean
8. autoFocus: 是否自动聚焦
    * Bollean
9. clearButtonMode: 显示清除按钮
    * 枚举类型: 'never', 'while-editing', 'unless-editing', 'always'
10. maxLength: 能够输入的最长字符数
11. enablesReturnKeyAutomatically:
    * Bollean
    * 如果为 true, 表示没有文本时键盘是不能有返回键的
12. returnKeyType: 软键盘返回显示的字符串
    * 枚举类型: 'default', 'go', 'google', 'join', 'next', 'route'
    * 'search', 'send', 'yahoo', 'done', 'emergency-call'
13. secureTextEntry:
    * Bollean
    * 如果为 true 则像密码框一样隐藏输入内容,默认值为 false
14. onChangeText:
    * Function
    * 当文本输入框的内容变化时, 调用该函数. 接收一个文本的参数对象
15. onChange
    * Function
    * 文本变化时, 调用该半数
16. onEndEditing
    * 结束编辑室,调用该函数
17. onBlur
    * 失去焦时触发事件
18. onFocus
    * 获得焦点时出发事件
19. onSubmitEditing
    * 结束编辑后, 点击键盘的提交按钮触发该事件
