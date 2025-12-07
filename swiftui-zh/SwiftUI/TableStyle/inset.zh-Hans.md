---
来源： https://developer.apple.com/documentation/SwiftUI/TableStyle/inset
抓取时间： 2025-12-03T06:11:03Z
---

# 插页

**类型属性**

表格样式，用于描述表格在内容和选区嵌入表格边缘时的行为和外观。

## 声明

```swift
@MainActor @preconcurrency static var inset: InsetTableStyle { get }
```

## 讨论

要自定义是否交替使用表格各行的背景，请使用 [alternatingRowBackgrounds(_:)](../View/alternatingRowBackgrounds.zh-Hans.md)。

## 获取内置表格样式

- **automatic**：当前上下文中的默认表格样式。
- **bordered**：描述带有标准边框的表格的行为和外观的表格样式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableStyle/inset
crawled: 2025-12-03T06:11:03Z
---

# inset

**Type Property**

The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.

## Declaration

```swift
@MainActor @preconcurrency static var inset: InsetTableStyle { get }
```

## Discussion

To customize whether the rows of the table should alternate their backgrounds, use [alternatingRowBackgrounds(_:)](../View/alternatingRowBackgrounds.zh-Hans.md).

## Getting built-in table styles

- **automatic**: The default table style in the current context.
- **bordered**: The table style that describes the behavior and appearance of a table with standard border.

