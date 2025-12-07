---
来源： https://developer.apple.com/documentation/SwiftUI/GridRow
抓取时间： 2025-12-02T17:27:13Z
---

# GridRow

**Structure**

二维网格容器中的水平行。

## 声明

```swift
@frozen struct GridRow<Content> where Content : View
```

## 概览

使用一个或多个`GridRow` 实例定义[Grid](Grid.zh-Hans.md) 容器的行。行内的子视图定义连续的网格单元格。你可以显式地向网格中添加行，或使用[ForEach](ForEach.zh-Hans.md) 结构生成多行。同样，您可以明确地向行添加单元格，也可以使用 [ForEach](ForEach.zh-Hans.md) 在行内生成多个单元格。下面的示例混合了这些策略：

```swift
Grid {
    GridRow {
        Color.clear
            .gridCellUnsizedAxes([.horizontal, .vertical])
        ForEach(1..<4) { column in
            Text("C\(column)")
        }
    }
    ForEach(1..<4) { row in
        GridRow {
            Text("R\(row)")
            ForEach(1..<4) { _ in
                Circle().foregroundStyle(.mint)
            }
        }
    }
}
```

上例中的网格有一个显式第一行和三个生成行。同样，每一行都有一个明确的第一单元格和三个生成单元格：



要创建空单元格，可以使用不可见的颜色，如上面示例中第一行第一列中出现的[clear](ShapeStyle/clear.zh-Hans.md) 颜色。但是，如果您使用的是[Color](Color.zh-Hans.md)或[Spacer](Spacer.zh-Hans.md)等灵活视图，您可能还需要添加[gridCellUnsizedAxes(_:)](View/gridCellUnsizedAxes.zh-Hans.md)修饰符，以防止视图占用的空间超过行或列中其他单元格所需的空间。



默认情况下，行中的单元格使用初始化[Alignment](Alignment.zh-Hans.md) 时定义的[Grid](Grid.zh-Hans.md)。不过，您可以通过向行的 [VerticalAlignment](VerticalAlignment.zh-Hans.md) 初始化器提供一个 [init(alignment:content:)](GridRow/init_alignment_content.zh-Hans.md) 值来覆盖行中单元格的垂直对齐方式。

如果对某行应用视图修饰符，则该行会对所有单元格应用该修饰符，这与[Group](Group.zh-Hans.md) 的行为类似。例如，如果将[border(_:width:)](View/border___width.zh-Hans.md)修饰符应用于行，SwiftUI 将在行中的每个单元格上绘制边框，而不是围绕行绘制边框。

## 创建网格行

- **init(alignment:content:)**：在网格中创建一行水平的子视图。

## 静态排列二维视图

- **Grid**：容器视图，用于将其他视图按二维布局排列。
- **gridCellColumns(_:)**：告诉作为网格中单元格的视图跨越指定的列数。
- **gridCellAnchor(_:)**：为作为网格单元格的视图指定自定义对齐锚点。
- **gridCellUnsizedAxes(_:)**：要求网格布局不在指定轴上为视图提供额外大小。
- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。

## 符合

- 可复制
- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/GridRow
crawled: 2025-12-02T17:27:13Z
---

# GridRow

**Structure**

A horizontal row in a two dimensional grid container.

## Declaration

```swift
@frozen struct GridRow<Content> where Content : View
```

## Overview

Use one or more `GridRow` instances to define the rows of a [Grid](Grid.zh-Hans.md) container. The child views inside the row define successive grid cells. You can add rows to the grid explicitly, or use the [ForEach](ForEach.zh-Hans.md) structure to generate multiple rows. Similarly, you can add cells to the row explicitly or you can use [ForEach](ForEach.zh-Hans.md) to generate multiple cells inside the row. The following example mixes these strategies:

```swift
Grid {
    GridRow {
        Color.clear
            .gridCellUnsizedAxes([.horizontal, .vertical])
        ForEach(1..<4) { column in
            Text("C\(column)")
        }
    }
    ForEach(1..<4) { row in
        GridRow {
            Text("R\(row)")
            ForEach(1..<4) { _ in
                Circle().foregroundStyle(.mint)
            }
        }
    }
}
```

The grid in the example above has an explicit first row and three generated rows. Similarly, each row has an explicit first cell and three generated cells:



To create an empty cell, use something invisible, like the [clear](ShapeStyle/clear.zh-Hans.md) color that appears in the first column of the first row in the example above. However, if you use a flexible view like a [Color](Color.zh-Hans.md) or a [Spacer](Spacer.zh-Hans.md), you might also need to add the [gridCellUnsizedAxes(_:)](View/gridCellUnsizedAxes.zh-Hans.md) modifier to prevent the view from taking up more space than the other cells in the row or column need.



By default, the cells in the row use the [Alignment](Alignment.zh-Hans.md) that you define when you initialize the [Grid](Grid.zh-Hans.md). However, you can override the vertical alignment for the cells in a row by providing a [VerticalAlignment](VerticalAlignment.zh-Hans.md) value to the row’s [init(alignment:content:)](GridRow/init_alignment_content.zh-Hans.md) initializer.

If you apply a view modifier to a row, the row applies the modifier to all of the cells, similar to how a [Group](Group.zh-Hans.md) behaves. For example,  if you apply the [border(_:width:)](View/border___width.zh-Hans.md) modifier to a row, SwiftUI draws a border on each cell in the row rather than around the row.

## Creating a grid row

- **init(alignment:content:)**: Creates a horizontal row of child views in a grid.

## Statically arranging views in two dimensions

- **Grid**: A container view that arranges other views in a two dimensional layout.
- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

## Conforms To

- Copyable
- View

