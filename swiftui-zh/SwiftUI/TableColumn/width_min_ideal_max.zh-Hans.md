---
来源：https://developer.apple.com/documentation/SwiftUI/TableColumn/width(min:ideal:max:)
抓取时间：2025-12-03T06:40:24Z
---

# width(min:ideal:max:)

**实例方法**

根据提供的约束条件创建可调整大小的表格列。

## 声明

```swift
nonisolated func width(min: CGFloat? = nil, ideal: CGFloat? = nil, max: CGFloat? = nil) -> TableColumn<RowValue, Sort, Content, Label>
```

## 参数

- **min**：可调整大小的列的最小宽度。如果非`nil`，该值必须大于或等于 `0`。
- **ideal**：列的理想宽度，用于确定表格列的初始宽度。列的起始宽度总是至少与设定的理想尺寸一样大，但如果表格的尺寸大于其所有列的理想尺寸，则列的起始宽度可能会更大。
- **max**：可调整列大小的最大宽度。如果非`nil`，该值必须大于 `0`。通过 doc://com.apple.documentation/documentation/CoreFoundation/CGFloat/1454161-infinity 表示无约束最大宽度。

## 讨论

调用此方法时，始终指定至少一个宽度约束。通过 `nil` 或省略约束表示不改变列的大小。

要创建固定大小的列，请使用 [width(_:)](width.zh-Hans.md)。

## 设置列宽

- **width(_:)**：创建固定宽度的表格列，用户不能调整其大小。
- **width()**：设置列的宽度。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumn/width(min:ideal:max:)
crawled: 2025-12-03T06:40:24Z
---

# width(min:ideal:max:)

**Instance Method**

Creates a resizable table column with the provided constraints.

## Declaration

```swift
nonisolated func width(min: CGFloat? = nil, ideal: CGFloat? = nil, max: CGFloat? = nil) -> TableColumn<RowValue, Sort, Content, Label>
```

## Parameters

- **min**: The minimum width of a resizable column. If non-`nil`, the value must be greater than or equal to `0`.
- **ideal**: The ideal width of the column, used to determine the initial width of the table column. The column always starts at least as large as the set ideal size, but may be larger if table was sized larger than the ideal of all of its columns.
- **max**: The maximum width of a resizable column. If non-`nil`, the value must be greater than `0`. Pass doc://com.apple.documentation/documentation/CoreFoundation/CGFloat/1454161-infinity to indicate unconstrained maximum width.

## Discussion

Always specify at least one width constraint when calling this method. Pass `nil` or leave out a constraint to indicate no change to the sizing of a column.

To create a fixed size column use [width(_:)](width.zh-Hans.md) instead.

## Setting the column width

- **width(_:)**: Creates a fixed width table column that isn’t user resizable.
- **width()**: Sets the column’s width.

