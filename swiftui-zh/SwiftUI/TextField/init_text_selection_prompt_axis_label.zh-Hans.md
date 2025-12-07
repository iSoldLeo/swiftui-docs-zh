---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(text:selection:prompt:axis:label:)
抓取时间：2025-12-02T17:51:50Z
---

# init(text:selection:prompt:axis:label:)

**Initializer**

创建一个文本字段，该字段与当前选区绑定，提示信息由`Text`生成。

## 声明

```swift
nonisolated init(text: Binding<String>, selection: Binding<TextSelection?>, prompt: Text? = nil, axis: Axis? = nil, @ViewBuilder label: () -> Label)
```

## 参数

- **text**：要显示和编辑的文本。
- **selection**：[Binding](../Binding.zh-Hans.md)：指向包含选中内容的变量的[Binding](../Binding.zh-Hans.md)。
- **prompt**：代表文本字段提示的`Text`，可指导用户在文本字段中输入什么内容。默认为 `nil`。
- **axis**：当可用空间不够时滚动文本的轴。默认为 `nil`。
- **label**：描述文本字段用途的视图。

## 讨论

下面的示例显示了一个与当前选择绑定的文本字段：

```swift
@State private var message: String = ""
@State private var selection: TextSelection? = nil

var body: some View {
    TextField(text: $message, selection: $selection) {
        Text("Message")
    }
}
```

使用[onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md)修饰符可在用户提交该文本字段时调用一个操作。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(text:selection:prompt:axis:label:)
crawled: 2025-12-02T17:51:50Z
---

# init(text:selection:prompt:axis:label:)

**Initializer**

Creates a text field with a binding to the current selection and a prompt generated from a `Text`.

## Declaration

```swift
nonisolated init(text: Binding<String>, selection: Binding<TextSelection?>, prompt: Text? = nil, axis: Axis? = nil, @ViewBuilder label: () -> Label)
```

## Parameters

- **text**: The text to display and edit.
- **selection**: A [Binding](../Binding.zh-Hans.md) to the variable containing the selection.
- **prompt**: A `Text` representing the prompt of the text field which provides users with guidance on what to type into the text field. Defaults to `nil`.
- **axis**: The axis in which to scroll text when it doesn’t fit in the available space. Defaults to `nil`.
- **label**: A view that describes the purpose of the text field.

## Discussion

The following example shows a text field with a binding to the current selection:

```swift
@State private var message: String = ""
@State private var selection: TextSelection? = nil

var body: some View {
    TextField(text: $message, selection: $selection) {
        Text("Message")
    }
}
```

Use the [onSubmit(of:_:)](../View/onSubmit_of.zh-Hans.md) modifier to invoke an action whenever the user submits this text field.

