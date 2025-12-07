---
来源： https://developer.apple.com/documentation/SwiftUI/TableStyle/bordered
抓取时间： 2025-12-03T06:11:04Z
---

# 边框

**类型属性**

表格样式，用于描述带有标准边框的表格的行为和外观。

## 声明

```swift
@MainActor @preconcurrency static var bordered: BorderedTableStyle { get }
```

## 讨论

有边框的表格应从其外部容器中嵌入，但没有嵌入样式的行或选择。

要自定义表格各行是否应交替显示背景，请使用 [alternatingRowBackgrounds(_:)](../View/alternatingRowBackgrounds.zh-Hans.md)。

## 获取内置表格样式

- **automatic**：当前上下文中的默认表格样式。
- **inset**：描述表格行为和外观的表格样式，其内容和选择从表格边缘嵌入。


---
source: https://developer.apple.com/documentation/SwiftUI/TableStyle/bordered
crawled: 2025-12-03T06:11:04Z
---

# bordered

**Type Property**

The table style that describes the behavior and appearance of a table with standard border.

## Declaration

```swift
@MainActor @preconcurrency static var bordered: BorderedTableStyle { get }
```

## Discussion

Bordered tables are expected to be inset from their outer containers, but do not have inset style rows or selection.

To customize whether the rows of the table should alternate their backgrounds, use [alternatingRowBackgrounds(_:)](../View/alternatingRowBackgrounds.zh-Hans.md).

## Getting built-in table styles

- **automatic**: The default table style in the current context.
- **inset**: The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.

