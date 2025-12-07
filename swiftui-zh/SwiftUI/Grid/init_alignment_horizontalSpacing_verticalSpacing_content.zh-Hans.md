--- 来源：https://developer.apple.com/documentation/SwiftUI/Grid/init(alignment:horizontalSpacing:verticalSpacing:content:)

抓取时间：2025-12-03T05:41:55Z

---

# init(alignment:horizontalSpacing:verticalSpacing:content:)

**Initializer**

创建一个具有指定间距、对齐方式和子视图的网格。

## 声明

```swift
init(alignment: Alignment = .center, horizontalSpacing: CGFloat? = nil, verticalSpacing: CGFloat? = nil, @ViewBuilder content: () -> Content)
```

## 参数

- **alignment**：用于在给定单元格分配的空间内对齐子视图的参考线。默认值为 [center](../Alignment/center.zh-Hans.md)。

- **horizontalSpacing**：每个单元格之间的水平距离，以磅为单位。默认值为 `nil`，这会产生适合平台的默认单元格间距。

- **verticalSpacing**：每个单元格之间的垂直距离，单位为磅。默认值为 `nil`，这会产生适合平台的默认单元格间距。

- **content**：用于创建网格行的闭包。

## 讨论

使用此初始化器创建 [Grid](../Grid.zh-Hans.md)。提供一个定义网格行的内容闭包，并可选择自定义单元格之间的间距以及每个单元格内内容的对齐方式。以下示例自定义单元格间距：

```swift
Grid(horizontalSpacing: 30, verticalSpacing: 30) {
    ForEach(0..<5) { row in
        GridRow {
            ForEach(0..<5) { column in
                Text("(\(column), \(row))")
            }
        }
    }
}
```

您可以直接列出行及其中的单元格，也可以使用 [ForEach](../ForEach.zh-Hans.md) 结构来生成它们，如上面的示例所示：

默认情况下，网格的对齐方式应用于网格中的所有单元格。但是，您也可以更改特定单元格或单元格组的对齐方式：

- 通过向相应行的 [init(alignment:content:)](../GridRow/init_alignment_content.zh-Hans.md) 初始化器指定 [VerticalAlignment](../VerticalAlignment.zh-Hans.md) 参数，覆盖行中单元格的垂直对齐方式。

- 通过向列中的一个单元格添加 [gridColumnAlignment(_:)](../View/gridColumnAlignment.zh-Hans.md) 视图修改器，并指定 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) 参数，覆盖列中单元格的水平对齐方式。

- 使用单元格视图上的 [gridCellAnchor(_:)](../View/gridCellAnchor.zh-Hans.md) 修饰符，为特定单元格指定自定义对齐锚点。


---
source: https://developer.apple.com/documentation/SwiftUI/Grid/init(alignment:horizontalSpacing:verticalSpacing:content:)
crawled: 2025-12-03T05:41:55Z
---

# init(alignment:horizontalSpacing:verticalSpacing:content:)

**Initializer**

Creates a grid with the specified spacing, alignment, and child views.

## Declaration

```swift
init(alignment: Alignment = .center, horizontalSpacing: CGFloat? = nil, verticalSpacing: CGFloat? = nil, @ViewBuilder content: () -> Content)
```

## Parameters

- **alignment**: The guide for aligning the child views within the space allocated for a given cell. The default is [center](../Alignment/center.zh-Hans.md).
- **horizontalSpacing**: The horizontal distance between each cell, given in points. The value is `nil` by default, which results in a default distance between cells that’s appropriate for the platform.
- **verticalSpacing**: The vertical distance between each cell, given in points. The value is `nil` by default, which results in a default distance between cells that’s appropriate for the platform.
- **content**: A closure that creates the grid’s rows.

## Discussion

Use this initializer to create a [Grid](../Grid.zh-Hans.md). Provide a content closure that defines the rows of the grid, and optionally customize the spacing between cells and the alignment of content within each cell. The following example customizes the spacing between cells:

```swift
Grid(horizontalSpacing: 30, verticalSpacing: 30) {
    ForEach(0..<5) { row in
        GridRow {
            ForEach(0..<5) { column in
                Text("(\(column), \(row))")
            }
        }
    }
}
```

You can list rows and the cells within rows directly, or you can use a [ForEach](../ForEach.zh-Hans.md) structure to generate either, as the example above does:



By default, the grid’s alignment value applies to all of the cells in the grid. However, you can also change the alignment for particular cells or groups of cells:

- Override the vertical alignment for the cells in a row by specifying a [VerticalAlignment](../VerticalAlignment.zh-Hans.md) parameter to the corresponding row’s [init(alignment:content:)](../GridRow/init_alignment_content.zh-Hans.md) initializer.
- Override the horizontal alignment for the cells in a column by adding a [gridColumnAlignment(_:)](../View/gridColumnAlignment.zh-Hans.md) view modifier to exactly one of the cells in the column, and specifying a [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) parameter.
- Specify a custom alignment anchor for a particular cell by using the [gridCellAnchor(_:)](../View/gridCellAnchor.zh-Hans.md) modifier on the cell’s view.

