--- 来源：https://developer.apple.com/documentation/SwiftUI/View/gridCellUnsizedAxes(_:)

抓取时间：2025-12-02T17:38:10Z

---

# gridCellUnsizedAxes(_:)

**实例方法**

要求网格布局不要在指定的轴上为视图分配额外的空间。

## 声明

```swift
nonisolated func gridCellUnsizedAxes(_ axes: Axis.Set) -> some View

```

## 参数

- **axes**：网格布局不应为视图分配任何可用空间的维度。这可以防止像 [Spacer](../Spacer.zh-Hans.md)、[Divider](../Divider.zh-Hans.md) 或 [Color](../Color.zh-Hans.md) 这样的灵活视图定义行或列的大小。

## 返回值

返回一个视图，该视图不会向其所在的网格系统请求在一个或多个轴上增加额外的空间。

## 说明

使用此修饰符可以防止灵活视图在指定的轴上占用比同一行或同一列中其他单元格所需空间更大的空间。例如，考虑以下 [Grid](../Grid.zh-Hans.md)，它会在两行内容之间放置一个 [Divider](../Divider.zh-Hans.md)：

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

文本和图像的宽度都与其内容相匹配。然而，由于分隔线会占用其父级提供的所有空间，网格会填充显示区域的宽度，并扩展所有其他单元格以匹配分隔线：

您可以通过添加带有 [horizontal](../Axis/horizontal.zh-Hans.md) 参数的修饰符来防止网格为分隔线分配超过其他单元格所需宽度的宽度：

```swift
Divider()
    .gridCellUnsizedAxes(.horizontal)
```

这将网格恢复到没有分隔线时的宽度：

## 静态排列二维视图

- **Grid**：用于在二维布局中排列其他视图的容器视图。

- **GridRow**：二维网格容器中的水平行。

- **gridCellColumns(_:)**：指示充当网格单元格的视图跨越指定的列数。

- **gridCellAnchor(_:)**：为用作网格单元格的视图指定自定义对齐锚点。

- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/gridCellUnsizedAxes(_:)
crawled: 2025-12-02T17:38:10Z
---

# gridCellUnsizedAxes(_:)

**Instance Method**

Asks grid layouts not to offer the view extra size in the specified axes.

## Declaration

```swift
nonisolated func gridCellUnsizedAxes(_ axes: Axis.Set) -> some View

```

## Parameters

- **axes**: The dimensions in which the grid shouldn’t offer the view a share of any available space. This prevents a flexible view like a [Spacer](../Spacer.zh-Hans.md), [Divider](../Divider.zh-Hans.md), or [Color](../Color.zh-Hans.md) from defining the size of a row or column.

## Return Value

A view that doesn’t ask an enclosing grid for extra size in one or more axes.

## Discussion

Use this modifier to prevent a flexible view from taking more space on the specified axes than the other cells in a row or column require. For example, consider the following [Grid](../Grid.zh-Hans.md) that places a [Divider](../Divider.zh-Hans.md) between two rows of content:

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

The text and images all have ideal widths for their content. However, because a divider takes as much space as its parent offers, the grid fills the width of the display, expanding all the other cells to match:



You can prevent the grid from giving the divider more width than the other cells require by adding the modifier with the [horizontal](../Axis/horizontal.zh-Hans.md) parameter:

```swift
Divider()
    .gridCellUnsizedAxes(.horizontal)
```

This restores the grid to the width that it would have without the divider:



## Statically arranging views in two dimensions

- **Grid**: A container view that arranges other views in a two dimensional layout.
- **GridRow**: A horizontal row in a two dimensional grid container.
- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

