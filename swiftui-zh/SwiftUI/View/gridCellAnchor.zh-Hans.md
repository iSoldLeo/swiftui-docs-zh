--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gridCellAnchor(_:)

抓取时间：2025-11-30T21:23:14Z

---

# gridCellAnchor(_:)

**实例方法**

为用作网格单元格的视图指定自定义对齐锚点。

## 声明

```swift
nonisolated func gridCellAnchor(_ anchor: UnitPoint) -> some View

```

## 参数

- **anchor**：定义视图在其网格单元格范围内如何对齐的单位点。

## 返回值

使用指定锚点对齐其内容的视图。

## 说明

网格（Grid）与堆栈和其他布局容器一样，使用对齐参考线执行大多数对齐操作。网格会沿 y 轴方向移动行中每个单元格的内容，直到该行中每个视图的指定参考线 [VerticalAlignment](../VerticalAlignment.zh-Hans.md) 与该行中所有其他视图的相同参考线对齐。类似地，网格会沿 x 轴方向调整视图，以对齐列中视图的参考线 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md)。有关典型的 SwiftUI 对齐操作的更多信息，请参阅参考线类型。

当您在网格中的视图上使用 `gridCellAnchor(_:)` 修饰符时，网格会将关联单元格的对齐策略更改为基于锚点的对齐策略。使用锚点对齐时，网格会将您指定的 [UnitPoint](../UnitPoint.zh-Hans.md) 投影到视图和单元格上，并对齐这两个投影。例如，考虑以下网格：

```swift
Grid(horizontalSpacing: 1, verticalSpacing: 1) {
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.red.frame(width: 60, height: 60)
    }
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.blue.frame(width: 10, height: 10)
            .gridCellAnchor(UnitPoint(x: 0.25, y: 0.75))
    }
}
```

网格会在第一行和第一列创建红色参考方块，以确定行和列的大小。如果没有锚点修饰符，由于网格默认的 [center](../Alignment/center.zh-Hans.md) 对齐方式，剩余单元格中的蓝色标记会出现在其单元格的中心。使用上述代码中所示的锚点修饰符后，网格会将标记的四分之一点与其所在单元格的四分之一点在 x 方向上对齐（x 方向的测量起点位于单元格左上角）。网格还会将标记的四分之三点与其所在单元格的四分之三点在 y 方向上对齐：

[UnitPoint](../UnitPoint.zh-Hans.md) 定义了许多与典型对齐参考线对应的便捷点，您也可以使用这些点。例如，您可以使用 [topTrailing](../UnitPoint/topTrailing.zh-Hans.md) 将单元格中视图的顶部和后边缘与单元格的顶部和后边缘对齐：

```swift
Color.blue.frame(width: 10, height: 10)
    .gridCellAnchor(.topTrailing)
```

将基于锚点的对齐策略应用于单个单元格不会影响网格在其他单元格上使用的对齐策略。 ### 合并单元格的锚点对齐

如果您使用 [gridCellColumns(_:)](gridCellColumns.zh-Hans.md) 修饰符使单元格跨越多列，或者如果您将视图放置在网格的行外，使其跨越整个网格，则网格会自动将其垂直和水平对齐参考线转换为合并单元格的单位点等效值，并对该单元格使用基于锚点的对齐方式。例如，以下网格通过将网格的默认对齐参考线 [center](../Alignment/center.zh-Hans.md) 转换为合并单元格中蓝色标记的锚点 [center](../UnitPoint/center.zh-Hans.md)，将标记放置在合并单元格的中心：

```swift
Grid(alignment: .center, horizontalSpacing: 1, verticalSpacing: 1) {
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.red.frame(width: 60, height: 60)
        Color.red.frame(width: 60, height: 60)
    }
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.blue.frame(width: 10, height: 10)
            .gridCellColumns(2)
    }
}
```

网格进行此转换的部分原因是避免歧义。每列都有自己的水平参考线，因此不清楚跨越多列的单元格应该与哪条参考线对齐。此外，在上面的示例中，第二列和第三列的居中对齐参考线都无法实现预期效果，即在合并单元格中将标记居中。锚点对齐可以实现此效果：

## 静态排列二维视图

- **Grid**：用于在二维布局中排列其他视图的容器视图。

- **GridRow**：二维网格容器中的水平行。

- **gridCellColumns(_:)**：指示用作网格单元格的视图跨越指定的列数。

- **gridCellUnsizedAxes(_:)**：要求网格布局不要在指定的轴上为视图提供额外的尺寸。

- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gridCellAnchor(_:)
crawled: 2025-11-30T21:23:14Z
---

# gridCellAnchor(_:)

**Instance Method**

Specifies a custom alignment anchor for a view that acts as a grid cell.

## Declaration

```swift
nonisolated func gridCellAnchor(_ anchor: UnitPoint) -> some View

```

## Parameters

- **anchor**: The unit point that defines how to align the view within the bounds of its grid cell.

## Return Value

A view that uses the specified anchor point to align its content.

## Discussion

Grids, like stacks and other layout containers, perform most alignment operations using alignment guides. The grid moves the contents of each cell in a row in the y direction until the specified [VerticalAlignment](../VerticalAlignment.zh-Hans.md) guide of each view in the row aligns with the same guide of all the other views in the row. Similarly, the grid aligns the [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) guides of views in a column by adjusting views in the x direction. See the guide types for more information about typical SwiftUI alignment operations.

When you use the `gridCellAnchor(_:)` modifier on a view in a grid, the grid changes to an anchor-based alignment strategy for the associated cell. With anchor alignment, the grid projects a [UnitPoint](../UnitPoint.zh-Hans.md) that you specify onto both the view and the cell, and aligns the two projections. For example, consider the following grid:

```swift
Grid(horizontalSpacing: 1, verticalSpacing: 1) {
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.red.frame(width: 60, height: 60)
    }
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.blue.frame(width: 10, height: 10)
            .gridCellAnchor(UnitPoint(x: 0.25, y: 0.75))
    }
}
```

The grid creates red reference squares in the first row and column to establish row and column sizes. Without the anchor modifier, the blue marker in the remaining cell would appear at the center of its cell, because of the grid’s default [center](../Alignment/center.zh-Hans.md) alignment. With the anchor modifier shown in the code above, the grid aligns the one quarter point of the marker with the one quarter point of its cell in the x direction, as measured from the origin at the top left of the cell. The grid also aligns the three quarters point of the marker with the three quarters point of the cell in the y direction:



[UnitPoint](../UnitPoint.zh-Hans.md) defines many convenience points that correspond to the typical alignment guides, which you can use as well. For example, you can use [topTrailing](../UnitPoint/topTrailing.zh-Hans.md) to align the top and trailing edges of a view in a cell with the top and trailing edges of the cell:

```swift
Color.blue.frame(width: 10, height: 10)
    .gridCellAnchor(.topTrailing)
```



Applying the anchor-based alignment strategy to a single cell doesn’t affect the alignment strategy that the grid uses on other cells.

### Anchor alignment for merged cells

If you use the [gridCellColumns(_:)](gridCellColumns.zh-Hans.md) modifier to cause a cell to span more than one column, or if you place a view in a grid outside of a row so that the view spans the entire grid, the grid automatically converts its vertical and horizontal alignment guides to the unit point equivalent for the merged cell, and uses an anchor-based approach for that cell. For example, the following grid places the marker at the center of the merged cell by converting the grid’s default [center](../Alignment/center.zh-Hans.md) alignment guide to a [center](../UnitPoint/center.zh-Hans.md) anchor for the blue marker in the merged cell:

```swift
Grid(alignment: .center, horizontalSpacing: 1, verticalSpacing: 1) {
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.red.frame(width: 60, height: 60)
        Color.red.frame(width: 60, height: 60)
    }
    GridRow {
        Color.red.frame(width: 60, height: 60)
        Color.blue.frame(width: 10, height: 10)
            .gridCellColumns(2)
    }
}
```

The grid makes this conversion in part to avoid ambiguity. Each column has its own horizontal guide, and it isn’t clear which of these a cell that spans multiple columns should align with. Further, in the example above, neither of the center alignment guides for the second or third column would provide the expected behavior, which is to center the marker in the merged cell. Anchor alignment provides this behavior:



## Statically arranging views in two dimensions

- **Grid**: A container view that arranges other views in a two dimensional layout.
- **GridRow**: A horizontal row in a two dimensional grid container.
- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

