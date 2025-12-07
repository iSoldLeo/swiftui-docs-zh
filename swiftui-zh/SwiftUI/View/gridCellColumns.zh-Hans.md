--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gridCellColumns(_:)

抓取时间：2025-11-30T21:23:13Z

---

# gridCellColumns(_:)

**实例方法**

指示网格中作为单元格的视图跨越指定数量的列。

## 声明

```swift
nonisolated func gridCellColumns(_ count: Int) -> some View

```

## 参数

- **count**：视图放置在网格行中时应占用的列数。

## 返回值

一个在网格行中占据指定列数的视图。

## 说明

默认情况下，放入 [GridRow](../GridRow.zh-Hans.md) 内容闭包中的每个视图都对应于网格中的一列。如果要使视图跨越多列，请应用 `gridCellColumns(_:)` 修饰符，如下一个典型的 macOS 配置视图示例所示：

```swift
Grid(alignment: .leadingFirstTextBaseline) {
    GridRow {
        Text("Regular font:")
            .gridColumnAlignment(.trailing)
        Text("Helvetica 12")
        Button("Select...") { }
    }
    GridRow {
        Text("Fixed-width font:")
        Text("Menlo Regular 11")
        Button("Select...") { }
    }
    GridRow {
        Color.clear
            .gridCellUnsizedAxes([.vertical, .horizontal])
        Toggle("Use fixed-width font for new documents", isOn: $isOn)
            .gridCellColumns(2) // Span two columns.
    }
}
```

上例中的 [Toggle](../Toggle.zh-Hans.md) 跨越了包含字体名称的列和包含按钮的列：

为了方便起见，您可以将视图直接放置在 [Grid](../Grid.zh-Hans.md) 的内容闭包中（位于 [GridRow](../GridRow.zh-Hans.md) 之外），并省略修饰符，从而使视图跨越所有 [Grid](../Grid.zh-Hans.md) 列。相反，要在一个单元格中包含多个视图，请使用合适的布局容器（例如 [HStack](../HStack.zh-Hans.md)）对视图进行分组，使它们像单个视图一样工作。

## 静态排列二维视图

- **Grid**：用于在二维布局中排列其他视图的容器视图。

- **GridRow**：二维网格容器中的水平行。

- **gridCellAnchor(_:)**：为用作网格单元格的视图指定自定义对齐锚点。

- **gridCellUnsizedAxes(_:)**：要求网格布局不要在指定的轴上为视图提供额外的尺寸。

- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gridCellColumns(_:)
crawled: 2025-11-30T21:23:13Z
---

# gridCellColumns(_:)

**Instance Method**

Tells a view that acts as a cell in a grid to span the specified number of columns.

## Declaration

```swift
nonisolated func gridCellColumns(_ count: Int) -> some View

```

## Parameters

- **count**: The number of columns that the view should consume when placed in a grid row.

## Return Value

A view that occupies the specified number of columns in a grid row.

## Discussion

By default, each view that you put into the content closure of a [GridRow](../GridRow.zh-Hans.md) corresponds to exactly one column of the grid. Apply the `gridCellColumns(_:)` modifier to a view that you want to span more than one column, as in the following example of a typical macOS configuration view:

```swift
Grid(alignment: .leadingFirstTextBaseline) {
    GridRow {
        Text("Regular font:")
            .gridColumnAlignment(.trailing)
        Text("Helvetica 12")
        Button("Select...") { }
    }
    GridRow {
        Text("Fixed-width font:")
        Text("Menlo Regular 11")
        Button("Select...") { }
    }
    GridRow {
        Color.clear
            .gridCellUnsizedAxes([.vertical, .horizontal])
        Toggle("Use fixed-width font for new documents", isOn: $isOn)
            .gridCellColumns(2) // Span two columns.
    }
}
```

The [Toggle](../Toggle.zh-Hans.md) in the example above spans the column that contains the font names and the column that contains the buttons:





As a convenience you can cause a view to span all of the [Grid](../Grid.zh-Hans.md) columns by placing the view directly in the content closure of the [Grid](../Grid.zh-Hans.md), outside of a [GridRow](../GridRow.zh-Hans.md), and omitting the modifier. To do the opposite and include more than one view in a cell, group the views using an appropriate layout container, like an [HStack](../HStack.zh-Hans.md), so that they act as a single view.

## Statically arranging views in two dimensions

- **Grid**: A container view that arranges other views in a two dimensional layout.
- **GridRow**: A horizontal row in a two dimensional grid container.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

