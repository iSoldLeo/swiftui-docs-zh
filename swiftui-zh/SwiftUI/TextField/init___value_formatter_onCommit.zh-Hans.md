---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:value:formatter:onCommit:)
抓取时间：2025-12-01T12:05:40Z


# init(_:value:formatter:onCommit:)

**Initializer**

创建一个绑定任意类型`V` 的实例。

## 声明

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, formatter: Formatter, onCommit: @escaping () -> Void) where S : StringProtocol
```

## 参数

- **title**：文本字段的标题，描述其用途。
- **value**：要编辑的基本值。
- **formatter**：在用户编辑的字符串和`V` 类型的基础值之间进行转换时使用的格式化格式。如果 `formatter` 无法执行转换，则不会修改 `binding.value`。
- **onCommit**：当文本字段有焦点时，用户执行操作（例如按 Return 键）时要执行的操作。

## 创建带值的文本字段

- **init(_:value:formatter:onEditingChanged:onCommit:)**：创建一个绑定任意类型的实例，`V`。
- **init(_:value:formatter:onEditingChanged:)**：创建一个绑定任意类型的实例，`V`。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:value:formatter:onCommit:)
crawled: 2025-12-01T12:05:40Z
---

# init(_:value:formatter:onCommit:)

**Initializer**

Create an instance which binds over an arbitrary type, `V`.

## Declaration

```swift
nonisolated init<S, V>(_ title: S, value: Binding<V>, formatter: Formatter, onCommit: @escaping () -> Void) where S : StringProtocol
```

## Parameters

- **title**: The title of the text field, describing its purpose.
- **value**: The underlying value to be edited.
- **formatter**: A formatter to use when converting between the string the user edits and the underlying value of type `V`. In the event that `formatter` is unable to perform the conversion, `binding.value` isn’t modified.
- **onCommit**: An action to perform when the user performs an action (for example, when the user presses the Return key) while the text field has focus.

## Creating a text field with a value

- **init(_:value:formatter:onEditingChanged:onCommit:)**: Create an instance which binds over an arbitrary type, `V`.
- **init(_:value:formatter:onEditingChanged:)**: Create an instance which binds over an arbitrary type, `V`.

