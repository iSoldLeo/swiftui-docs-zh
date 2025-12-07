---
来源： https://developer.apple.com/documentation/SwiftUI/Grid
抓取时间： 2025-12-02T17:27:12Z
---

# 网格

**Structure**

一种容器视图，可按二维布局排列其他视图。

## 声明

```swift
@frozen struct Grid<Content> where Content : View
```

## 概览

通过使用[GridRow](GridRow.zh-Hans.md) 结构集合初始化`Grid`，创建二维布局。每个网格行中的第一个视图出现在网格的第一列，第二个视图出现在第二列，依此类推。下面的示例创建了一个两行两列的网格：

```swift
Grid {
    GridRow {
        Text("Hello")
        Image(systemName: "globe")
    }
    GridRow {
        Image(systemName: "hand.wave")
        Text("World")
    }
}
```

网格及其行的行为类似于用[HStack](HStack.zh-Hans.md) 实例包裹的[VStack](VStack.zh-Hans.md) 实例集合。不过，网格是将行和列的创建作为单个操作来处理的，它将对齐方式和间距应用于单元格，而不是先应用于行，然后再应用于一列不相关的行。上面示例中生成的网格演示了这一点：





### 多栏单元格

如果你在网格内容中提供了视图而不是[GridRow](GridRow.zh-Hans.md) 作为元素，网格就会使用视图来创建横跨网格所有列的行。例如，你可以在上一示例的行之间添加一个[Divider](Divider.zh-Hans.md)：

```swift
Grid {
    GridRow {
        Text("Hello")
        Image(systemName: "globe")
    }
    Divider()
    GridRow {
        Image(systemName: "hand.wave")
        Text("World")
    }
}
```

由于分隔线占用的水平空间与其父视图相同，因此整个网格会变宽，以填充其父视图所提供的宽度。



要防止灵活视图在给定轴上占用的空间超过行或列中其他单元格所需的空间，可在视图中添加[gridCellUnsizedAxes(_:)](View/gridCellUnsizedAxes.zh-Hans.md)视图修饰符：

```swift
Divider()
    .gridCellUnsizedAxes(.horizontal)
```

这样就可以将网格恢复到文本和图像所需的宽度：



要使单元格跨特定列数而不是整个网格，请在⟦内包含⟦的视图上使用[gridCellColumns(_:)](View/gridCellColumns.zh-Hans.md)修改器。

### 列数

网格列数的增长是为了处理列数最大的行。如果创建列数不同的行，网格会在列数较少的行的尾部添加空单元格。下面的示例创建了三条列数不同的行：

```swift
Grid {
    GridRow {
        Text("Row 1")
        ForEach(0..<2) { _ in Color.red }
    }
    GridRow {
        Text("Row 2")
        ForEach(0..<5) { _ in Color.green }
    }
    GridRow {
        Text("Row 3")
        ForEach(0..<4) { _ in Color.blue }
    }
}
```

生成的网格的列数与最宽行的列数相同，并为未指定足够视图的行添加空单元格：



网格会设置一列中所有单元格的宽度，以满足该列最宽单元格的需要。在上例中，第一列的宽度取决于该列包含的最宽[Text](Text.zh-Hans.md) 视图的宽度。其他列包含灵活的[Color](Color.zh-Hans.md) 视图，它们平分网格父视图提供的剩余水平空间。

同样，一行中最高的单元格会设定整行的高度。上述网格第一列中的单元格只需要每个字符串所需的高度，但[Color](Color.zh-Hans.md)单元格则会扩展，以平均分配网格的总高度。因此，颜色单元格决定了行的高度。

### 单元格间距和对齐方式

使用 [init(alignment:horizontalSpacing:verticalSpacing:content:)](Grid/init_alignment_horizontalSpacing_verticalSpacing_content.zh-Hans.md) 初始化器初始化网格时，你可以控制单元格在水平和垂直方向上的间距，并为所有网格单元格中的内容设置默认对齐方式。请看上一示例的修改版：

```swift
Grid(alignment: .bottom, horizontalSpacing: 1, verticalSpacing: 1) {
    // ...
}
```

这种配置会使所有单元格都使用[bottom](Alignment/bottom.zh-Hans.md) 对齐方式--这只影响文本单元格，因为颜色完全填满了它们的单元格--并且会减小单元格之间的间距：



你可以覆盖特定单元格或单元格组的对齐方式。例如，你可以通过添加[gridColumnAlignment(_:)](View/gridColumnAlignment.zh-Hans.md)修饰符来改变列中单元格的水平对齐方式，或者通过配置行的[init(alignment:content:)](GridRow/init_alignment_content.zh-Hans.md)初始化器来改变行中单元格的垂直对齐方式。您还可以使用[gridCellAnchor(_:)](View/gridCellAnchor.zh-Hans.md)修改器对齐单个单元格。

### 性能注意事项

网格可以正确调整行和列的大小，因为它会立即渲染其所有子视图。如果您的应用程序在首次显示出现在[ScrollView](ScrollView.zh-Hans.md) 中的大型网格时性能不佳，请考虑改用[LazyVGrid](LazyVGrid.zh-Hans.md) 或 [LazyHGrid](LazyHGrid.zh-Hans.md)。

懒网格会在 SwiftUI 需要显示单元格时才显示单元格，而不是一次性全部显示。这降低了显示从未完全可见的大型可滚动网格的初始成本，但也降低了网格优化单元格布局的能力。只有在对代码进行剖析后发现性能有明显改善时，才能切换到懒网格。

## 创建网格

- **init(alignment:horizontalSpacing:verticalSpacing:content:)**：以指定的间距、对齐方式和子视图创建网格。

## 静态排列二维视图

- **GridRow**：二维网格容器中的水平行。
- **gridCellColumns(_:)**：告诉作为网格中单元格的视图跨越指定的列数。
- **gridCellAnchor(_:)**：为作为网格单元格的视图指定自定义对齐锚点。
- **gridCellUnsizedAxes(_:)**：要求网格布局不在指定轴上为视图提供额外大小。
- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。

## 符合

- 可复制
- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/Grid
crawled: 2025-12-02T17:27:12Z
---

# Grid

**Structure**

A container view that arranges other views in a two dimensional layout.

## Declaration

```swift
@frozen struct Grid<Content> where Content : View
```

## Overview

Create a two dimensional layout by initializing a `Grid` with a collection of [GridRow](GridRow.zh-Hans.md) structures. The first view in each grid row appears in the grid’s first column, the second view in the second column, and so on. The following example creates a grid with two rows and two columns:

```swift
Grid {
    GridRow {
        Text("Hello")
        Image(systemName: "globe")
    }
    GridRow {
        Image(systemName: "hand.wave")
        Text("World")
    }
}
```

A grid and its rows behave something like a collection of [HStack](HStack.zh-Hans.md) instances wrapped in a [VStack](VStack.zh-Hans.md). However, the grid handles row and column creation as a single operation, which applies alignment and spacing to cells, rather than first to rows and then to a column of unrelated rows. The grid produced by the example above demonstrates this:





### Multicolumn cells

If you provide a view rather than a [GridRow](GridRow.zh-Hans.md) as an element in the grid’s content, the grid uses the view to create a row that spans all of the grid’s columns. For example, you can add a [Divider](Divider.zh-Hans.md) between the rows of the previous example:

```swift
Grid {
    GridRow {
        Text("Hello")
        Image(systemName: "globe")
    }
    Divider()
    GridRow {
        Image(systemName: "hand.wave")
        Text("World")
    }
}
```

Because a divider takes as much horizontal space as its parent offers, the entire grid widens to fill the width offered by its parent view.



To prevent a flexible view from taking more space on a given axis than the other cells in a row or column require, add the [gridCellUnsizedAxes(_:)](View/gridCellUnsizedAxes.zh-Hans.md) view modifier to the view:

```swift
Divider()
    .gridCellUnsizedAxes(.horizontal)
```

This restores the grid to the width that the text and images require:



To make a cell span a specific number of columns rather than the whole grid, use the [gridCellColumns(_:)](View/gridCellColumns.zh-Hans.md) modifier on a view that’s contained inside a [GridRow](GridRow.zh-Hans.md).

### Column count

The grid’s column count grows to handle the row with the largest number of columns. If you create rows with different numbers of columns, the grid adds empty cells to the trailing edge of rows that have fewer columns. The example below creates three rows with different column counts:

```swift
Grid {
    GridRow {
        Text("Row 1")
        ForEach(0..<2) { _ in Color.red }
    }
    GridRow {
        Text("Row 2")
        ForEach(0..<5) { _ in Color.green }
    }
    GridRow {
        Text("Row 3")
        ForEach(0..<4) { _ in Color.blue }
    }
}
```

The resulting grid has as many columns as the widest row, adding empty cells to rows that don’t specify enough views:



The grid sets the width of all the cells in a column to match the needs of column’s widest cell. In the example above, the width of the first column depends on the width of the widest [Text](Text.zh-Hans.md) view that the column contains. The other columns, which contain flexible [Color](Color.zh-Hans.md) views, share the remaining horizontal space offered by the grid’s parent view equally.

Similarly, the tallest cell in a row sets the height of the entire row. The cells in the first column of the grid above need only the height required for each string, but the [Color](Color.zh-Hans.md) cells expand to equally share the total height available to the grid. As a result, the color cells determine the row heights.

### Cell spacing and alignment

You can control the spacing between cells in both the horizontal and vertical dimensions and set a default alignment for the content in all the grid cells when you initialize the grid using the [init(alignment:horizontalSpacing:verticalSpacing:content:)](Grid/init_alignment_horizontalSpacing_verticalSpacing_content.zh-Hans.md) initializer. Consider a modified version of the previous example:

```swift
Grid(alignment: .bottom, horizontalSpacing: 1, verticalSpacing: 1) {
    // ...
}
```

This configuration causes all of the cells to use [bottom](Alignment/bottom.zh-Hans.md) alignment — which only affects the text cells because the colors fill their cells completely — and it reduces the spacing between cells:



You can override the alignment of specific cells or groups of cells. For example, you can change the horizontal alignment of the cells in a column by adding the [gridColumnAlignment(_:)](View/gridColumnAlignment.zh-Hans.md) modifier, or the vertical alignment of the cells in a row by configuring the row’s [init(alignment:content:)](GridRow/init_alignment_content.zh-Hans.md) initializer. You can also align a single cell with the [gridCellAnchor(_:)](View/gridCellAnchor.zh-Hans.md) modifier.

### Performance considerations

A grid can size its rows and columns correctly because it renders all of its child views immediately. If your app exhibits poor performance when it first displays a large grid that appears inside a [ScrollView](ScrollView.zh-Hans.md), consider switching to a [LazyVGrid](LazyVGrid.zh-Hans.md) or [LazyHGrid](LazyHGrid.zh-Hans.md) instead.

Lazy grids render their cells when SwiftUI needs to display them, rather than all at once. This reduces the initial cost of displaying a large scrollable grid that’s never fully visible, but also reduces the grid’s ability to optimally lay out cells. Switch to a lazy grid only if profiling your code shows a worthwhile performance improvement.

## Creating a grid

- **init(alignment:horizontalSpacing:verticalSpacing:content:)**: Creates a grid with the specified spacing, alignment, and child views.

## Statically arranging views in two dimensions

- **GridRow**: A horizontal row in a two dimensional grid container.
- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

## Conforms To

- Copyable
- View

