---
来源：https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:)
抓取时间：2025-12-02T17:51:39Z
---

# init(_:text:)

**Initializer**

创建文本字段，其文本标签由本地化标题字符串生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>)
```

## 参数

- **titleKey**：文本字段本地化标题的键值，描述其用途。
- **text**：要显示和编辑的文本。

## 使用字符串创建文本字段

- **init(_:text:prompt:)**：用本地化标题字符串生成的文本标签创建文本字段。
- **init(text:prompt:label:)**：`Text`.SY_0003⟧： 创建带有提示的文本字段，提示由本地化标题字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/TextField/init(_:text:)
crawled: 2025-12-02T17:51:39Z
---

# init(_:text:)

**Initializer**

Creates a text field with a text label generated from a localized title string.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, text: Binding<String>)
```

## Parameters

- **titleKey**: The key for the localized title of the text field, describing its purpose.
- **text**: The text to display and edit.

## Creating a text field with a string

- **init(_:text:prompt:)**: Creates a text field with a text label generated from a localized title string.
- **init(text:prompt:label:)**: Creates a text field with a prompt generated from a `Text`.

