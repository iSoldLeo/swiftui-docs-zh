---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:onEditingChanged:)
抓取时间：2025-12-03T07:16:31Z
---

# init(_:text:onEditingChanged:)

**Initializer**

创建一个文本字段，其文本标签由本地化标题字符串生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onEditingChanged: @escaping (Bool) -> Void)
```

## 参数

- **titleKey**：文本字段本地化标题的键值，描述其用途。
- **text**：要显示和编辑的文本。
- **onEditingChanged**：要显示和编辑的文本：当用户开始编辑`text` 和完成编辑`text` 后要执行的操作。闭包接收一个布尔值，表示编辑状态：当用户开始编辑时为`true`，当用户完成编辑时为`false`。

## 使用字符串创建文本字段

- **init(_:text:onEditingChanged:onCommit:)**：用本地化标题字符串生成的文本标签创建文本字段。
- **init(_:text:onCommit:)**：创建文本字段，文本标签由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:onEditingChanged:)
crawled: 2025-12-03T07:16:31Z
---

# init(_:text:onEditingChanged:)

**Initializer**

Creates a text field with a text label generated from a localized title string.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>, onEditingChanged: @escaping (Bool) -> Void)
```

## Parameters

- **titleKey**: The key for the localized title of the text field, describing its purpose.
- **text**: The text to display and edit.
- **onEditingChanged**: The action to perform when the user begins editing `text` and after the user finishes editing `text`. The closure receives a Boolean value that indicates the editing status: `true` when the user begins editing, `false` when they finish.

## Creating a text field with a string

- **init(_:text:onEditingChanged:onCommit:)**: Creates a text field with a text label generated from a localized title string.
- **init(_:text:onCommit:)**: Creates a text field with a text label generated from a localized title string.

