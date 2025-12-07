---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:onEditingChanged:onCommit:)
抓取时间：2025-12-01T12:05:37Z
---

# init(_:text:onEditingChanged:onCommit:)

**Initializer**

创建一个文本字段，其文本标签由本地化标题字符串生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onEditingChanged: @escaping (Bool) -> Void, onCommit: @escaping () -> Void)
```

## 参数

- **titleKey**：文本字段本地化标题的键值，描述其用途。
- **text**：要显示和编辑的文本。
- **onEditingChanged**：要显示和编辑的文本：当用户开始编辑`text` 和完成编辑`text` 后要执行的操作。闭包接收一个布尔值，表示编辑状态：`true` 表示用户开始编辑，`false` 表示用户完成编辑。
- **onCommit**：在文本字段有焦点时，当用户执行操作（例如按回车键）时要执行的操作。

## 使用字符串创建文本字段

- **init(_:text:onCommit:)**：用本地化标题字符串生成的文本标签创建文本字段。
- **init(_:text:onEditingChanged:)**：创建文本字段，文本标签由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:onEditingChanged:onCommit:)
crawled: 2025-12-01T12:05:37Z
---

# init(_:text:onEditingChanged:onCommit:)

**Initializer**

Creates a text field with a text label generated from a localized title string.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onEditingChanged: @escaping (Bool) -> Void, onCommit: @escaping () -> Void)
```

## Parameters

- **titleKey**: The key for the localized title of the text field, describing its purpose.
- **text**: The text to display and edit.
- **onEditingChanged**: The action to perform when the user begins editing `text` and after the user finishes editing `text`. The closure receives a Boolean value that indicates the editing status: `true` when the user begins editing, `false` when they finish.
- **onCommit**: An action to perform when the user performs an action (for example, when the user presses the Return key) while the text field has focus.

## Creating a text field with a string

- **init(_:text:onCommit:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:onEditingChanged:)**: Creates a text field with a text label generated from a localized title string.

