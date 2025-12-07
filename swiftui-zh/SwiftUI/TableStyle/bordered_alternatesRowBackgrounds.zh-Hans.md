---
来源： https://developer.apple.com/documentation/SwiftUI/TableStyle/bordered(alternatesRowBackgrounds:)
抓取时间：2025-12-01T11:00:06Z
---

# bordered(alternatesRowBackgrounds:)

**类型方法**

表格样式，用于描述带有标准边框的表格的行为和外观。

## 声明

```swift
@MainActor @preconcurrency static func bordered(alternatesRowBackgrounds: Bool) -> BorderedTableStyle
```

## 参数

- **alternatesRowBackgrounds**：是否交替显示各行的背景，以便在视觉上区分它们。

## 讨论

有边框的表格应从其外部容器中嵌入，但没有嵌入样式的行或选区。

## 过时样式

- **inset(alternatesRowBackgrounds:)**：表格样式，用于描述内容和选区从表格边缘嵌入时表格的行为和外观。


---
source: https://developer.apple.com/documentation/SwiftUI/TableStyle/bordered(alternatesRowBackgrounds:)
crawled: 2025-12-01T11:00:06Z
---

# bordered(alternatesRowBackgrounds:)

**Type Method**

The table style that describes the behavior and appearance of a table with standard border.

## Declaration

```swift
@MainActor @preconcurrency static func bordered(alternatesRowBackgrounds: Bool) -> BorderedTableStyle
```

## Parameters

- **alternatesRowBackgrounds**: Whether the rows should alternate their backgrounds to help visually distinguish them from each other.

## Discussion

Bordered tables are expected to be inset from their outer containers, but do not have inset style rows or selection.

## Deprecated styles

- **inset(alternatesRowBackgrounds:)**: The table style that describes the behavior and appearance of a table with its content and selection inset from the table edges.

