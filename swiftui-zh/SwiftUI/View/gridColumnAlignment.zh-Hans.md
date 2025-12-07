--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gridColumnAlignment(_:)

抓取时间：2025-12-02T17:38:11Z

---

# gridColumnAlignment(_:)

**实例方法**

覆盖视图所在网格列的默认水平对齐方式。

## 声明

```swift
nonisolated func gridColumnAlignment(_ guide: HorizontalAlignment) -> some View

```

## 参数

- **guide**：视图所在网格列的 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) 指南。

## 返回值

一个使用指定水平对齐方式的视图，使网格中同一列的所有单元格使用相同的对齐方式。

## 讨论

使用 [init(alignment:horizontalSpacing:verticalSpacing:content:)](../Grid/init_alignment_horizontalSpacing_verticalSpacing_content.zh-Hans.md) 初始化器创建网格时，您可以设置网格中单元格在垂直和水平方向上的默认对齐方式。但是，您可以使用 `gridColumnAlignment(_:)` 修饰符来覆盖网格中某一列的水平对齐方式。以下示例将网格的对齐方式设置为 [leadingFirstTextBaseline](../Alignment/leadingFirstTextBaseline.zh-Hans.md)，然后将第一列的对齐方式设置为 [trailing](../HorizontalAlignment/trailing.zh-Hans.md)：

```swift
Grid(alignment: .leadingFirstTextBaseline) {
    GridRow {
        Text("Regular font:")
            .gridColumnAlignment(.trailing) // Align the entire first column.
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
            .gridCellColumns(2)
    }
}
```

这将创建典型的 macOS 配置视图布局，其中第一列的后边缘与第二列的前边缘对齐：

只需将修饰符添加到列中的一个单元格即可。网格会自动将该列中的所有单元格以相同的方式对齐。如果对同一列中的不同单元格应用不同的对齐方式，则会出现未定义行为。

要覆盖行对齐方式，请参阅 [init(alignment:content:)](../GridRow/init_alignment_content.zh-Hans.md)。要覆盖单个单元格的对齐方式，请参阅 [gridCellAnchor(_:)](gridCellAnchor.zh-Hans.md)。

## 静态排列二维视图

- **Grid**：用于在二维布局中排列其他视图的容器视图。

- **GridRow**：二维网格容器中的水平行。

- **gridCellColumns(_:)**：指示用作网格单元格的视图跨越指定的列数。

- **gridCellAnchor(_:)**：为用作网格单元格的视图指定自定义对齐锚点。

- **gridCellUnsizedAxes(_:)**：要求网格布局不要在指定的轴上为视图提供额外的尺寸。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gridColumnAlignment(_:)
crawled: 2025-12-02T17:38:11Z
---

# gridColumnAlignment(_:)

**Instance Method**

Overrides the default horizontal alignment of the grid column that the view appears in.

## Declaration

```swift
nonisolated func gridColumnAlignment(_ guide: HorizontalAlignment) -> some View

```

## Parameters

- **guide**: The [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) guide to use for the grid column that the view appears in.

## Return Value

A view that uses the specified horizontal alignment, and that causes all cells in the same column of a grid to use the same alignment.

## Discussion

You set a default alignment for the cells in a grid in both vertical and horizontal dimensions when you create the grid with the [init(alignment:horizontalSpacing:verticalSpacing:content:)](../Grid/init_alignment_horizontalSpacing_verticalSpacing_content.zh-Hans.md) initializer. However, you can use the `gridColumnAlignment(_:)` modifier to override the horizontal alignment of a column within the grid. The following example sets a grid’s alignment to [leadingFirstTextBaseline](../Alignment/leadingFirstTextBaseline.zh-Hans.md), and then sets the first column to use [trailing](../HorizontalAlignment/trailing.zh-Hans.md) alignment:

```swift
Grid(alignment: .leadingFirstTextBaseline) {
    GridRow {
        Text("Regular font:")
            .gridColumnAlignment(.trailing) // Align the entire first column.
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
            .gridCellColumns(2)
    }
}
```

This creates the layout of a typical macOS configuration view, with the trailing edge of the first column flush with the leading edge of the second column:



Add the modifier to only one cell in a column. The grid automatically aligns all cells in that column the same way. You get undefined behavior if you apply different alignments to different cells in the same column.

To override row alignment, see [init(alignment:content:)](../GridRow/init_alignment_content.zh-Hans.md). To override alignment for a single cell, see [gridCellAnchor(_:)](gridCellAnchor.zh-Hans.md).

## Statically arranging views in two dimensions

- **Grid**: A container view that arranges other views in a two dimensional layout.
- **GridRow**: A horizontal row in a two dimensional grid container.
- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.

