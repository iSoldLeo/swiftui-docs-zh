---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:onCommit:)
抓取时间：2025-12-03T07:16:30Z


# init(_:text:onCommit:)

**Initializer**

创建一个文本字段，其文本标签由本地化标题字符串生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onCommit: @escaping () -> Void)
```

## 参数

- **titleKey**：文本字段本地化标题的键值，描述其用途。
- **text**：要显示和编辑的文本。
- **onCommit**：要显示和编辑的文本：当文本字段有焦点时，当用户执行操作（例如按 Return 键）时要执行的操作。

## 使用字符串创建文本字段

- **init(_:text:onEditingChanged:onCommit:)**：用本地化标题字符串生成的文本标签创建文本字段。
- **init(_:text:onEditingChanged:)**：创建文本字段，文本标签由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:onCommit:)
crawled: 2025-12-03T07:16:30Z
---

# init(_:text:onCommit:)

**Initializer**

Creates a text field with a text label generated from a localized title string.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onCommit: @escaping () -> Void)
```

## Parameters

- **titleKey**: The key for the localized title of the text field, describing its purpose.
- **text**: The text to display and edit.
- **onCommit**: An action to perform when the user performs an action (for example, when the user presses the Return key) while the text field has focus.

## Creating a text field with a string

- **init(_:text:onEditingChanged:onCommit:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:onEditingChanged:)**: Creates a text field with a text label generated from a localized title string.

