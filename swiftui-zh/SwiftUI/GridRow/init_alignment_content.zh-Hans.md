--- 来源：https://developer.apple.com/documentation/SwiftUI/GridRow/init(alignment:content:)

抓取时间：2025-12-01T10:31:07Z

---

# init(alignment:content:)

**Initializer**

在网格中创建一行水平排列的子视图。

## 声明

```swift
init(alignment: VerticalAlignment? = nil, @ViewBuilder content: () -> Content)
```

## 参数

- **alignment**：行的可选 [VerticalAlignment](../VerticalAlignment.zh-Hans.md) 值。如果未指定值，则行将使用网格初始化器中指定的 [Alignment](../Alignment.zh-Hans.md) 参数的垂直对齐方式，默认值为 [center](../VerticalAlignment/center.zh-Hans.md)。

- **content**：包含子视图的构建器闭包。闭包中的每个视图都隐式映射到网格中的一个单元格。

## 讨论

使用此初始化器在 [Grid](../Grid.zh-Hans.md) 内部创建一个 [GridRow](../GridRow.zh-Hans.md)。提供一个内容闭包来定义行中的单元格，并可选择自定义每个单元格内内容的垂直对齐方式。以下示例自定义了第一行和第三行中单元格的垂直对齐方式：

```swift
Grid(alignment: .trailing) {
    GridRow(alignment: .top) { // Use top vertical alignment.
        Text("Top")
        Color.red.frame(width: 1, height: 50)
        Color.blue.frame(width: 50, height: 1)
    }
    GridRow { // Use the default (center) alignment.
        Text("Center")
        Color.red.frame(width: 1, height: 50)
        Color.blue.frame(width: 50, height: 1)
    }
    GridRow(alignment: .bottom) { // Use bottom vertical alignment.
        Text("Bottom")
        Color.red.frame(width: 1, height: 50)
        Color.blue.frame(width: 50, height: 1)
    }
}
```

上面的示例指定了网格的 [trailing](../Alignment/trailing.zh-Hans.md) 对齐方式，该对齐方式由 [center](../VerticalAlignment/center.zh-Hans.md) 垂直对齐和 [trailing](../HorizontalAlignment/trailing.zh-Hans.md) 水平对齐组成。中间一行使用居中垂直对齐，但其他两行指定了自定义垂直对齐方式：

要覆盖列对齐方式，请使用 [gridColumnAlignment(_:)](../View/gridColumnAlignment.zh-Hans.md)。要覆盖单个单元格的对齐方式，请使用 [gridCellAnchor(_:)](../View/gridCellAnchor.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/GridRow/init(alignment:content:)
crawled: 2025-12-01T10:31:07Z
---

# init(alignment:content:)

**Initializer**

Creates a horizontal row of child views in a grid.

## Declaration

```swift
init(alignment: VerticalAlignment? = nil, @ViewBuilder content: () -> Content)
```

## Parameters

- **alignment**: An optional [VerticalAlignment](../VerticalAlignment.zh-Hans.md) for the row. If you don’t specify a value, the row uses the vertical alignment component of the [Alignment](../Alignment.zh-Hans.md) parameter that you specify in the grid’s [init(alignment:horizontalSpacing:verticalSpacing:content:)](../Grid/init_alignment_horizontalSpacing_verticalSpacing_content.zh-Hans.md) initializer, which is [center](../VerticalAlignment/center.zh-Hans.md) by default.
- **content**: The builder closure that contains the child views. Each view in the closure implicitly maps to a cell in the grid.

## Discussion

Use this initializer to create a [GridRow](../GridRow.zh-Hans.md) inside of a [Grid](../Grid.zh-Hans.md). Provide a content closure that defines the cells of the row, and optionally customize the vertical alignment of content within each cell. The following example customizes the vertical alignment of the cells in the first and third rows:

```swift
Grid(alignment: .trailing) {
    GridRow(alignment: .top) { // Use top vertical alignment.
        Text("Top")
        Color.red.frame(width: 1, height: 50)
        Color.blue.frame(width: 50, height: 1)
    }
    GridRow { // Use the default (center) alignment.
        Text("Center")
        Color.red.frame(width: 1, height: 50)
        Color.blue.frame(width: 50, height: 1)
    }
    GridRow(alignment: .bottom) { // Use bottom vertical alignment.
        Text("Bottom")
        Color.red.frame(width: 1, height: 50)
        Color.blue.frame(width: 50, height: 1)
    }
}
```

The example above specifies [trailing](../Alignment/trailing.zh-Hans.md) alignment for the grid, which is composed of [center](../VerticalAlignment/center.zh-Hans.md) vertical alignment and [trailing](../HorizontalAlignment/trailing.zh-Hans.md) horizontal alignment. The middle row relies on the center vertical alignment, but the other two rows specify custom vertical alignments:





To override column alignment, use [gridColumnAlignment(_:)](../View/gridColumnAlignment.zh-Hans.md). To override alignment for a single cell, use [gridCellAnchor(_:)](../View/gridCellAnchor.zh-Hans.md).

