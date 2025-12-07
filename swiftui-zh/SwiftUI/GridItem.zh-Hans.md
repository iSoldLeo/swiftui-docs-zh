---
来源： https://developer.apple.com/documentation/SwiftUI/GridItem
抓取时间： 2025-12-02T17:38:11Z
---

# 网格项目

**Structure**

对懒人网格中某一行或某一列的描述。

## 声明

```swift
struct GridItem
```

## 概览

使用`GridItem` 实例数组配置懒网格中项的布局。数组中的每个网格项都指定了布局属性，如[LazyHGrid](LazyHGrid.zh-Hans.md) 行或[LazyVGrid](LazyVGrid.zh-Hans.md) 列的大小和间距。下面的示例为水平网格定义了四行，每行都有不同的特性：

```swift
struct GridItemDemo: View {
    let rows = [
        GridItem(.fixed(30), spacing: 1),
        GridItem(.fixed(60), spacing: 10),
        GridItem(.fixed(90), spacing: 20),
        GridItem(.fixed(10), spacing: 50)
    ]

    var body: some View {
        ScrollView(.horizontal) {
            LazyHGrid(rows: rows, spacing: 5) {
                ForEach(0...300, id: \.self) { _ in
                    Color.red.frame(width: 30)
                    Color.green.frame(width: 30)
                    Color.blue.frame(width: 30)
                    Color.yellow.frame(width: 30)
                }
            }
        }
    }
}
```

懒惰水平网格根据列中最宽的单元格设置每列的宽度。之所以能做到这一点，是因为它能同时访问给定列中的所有视图。在上面的示例中，[Color](Color.zh-Hans.md) 视图始终具有相同的固定宽度，因此整个网格的列宽是一致的。

但是，懒惰水平网格通常无法访问一行中的所有视图，因为它会在用户滚动浏览应用中的信息时生成新的单元格。相反，它依靠网格项来获取每一行的信息。上面的示例为每一行指定了不同的固定高度，并在每一行后设置了不同的间距：



## 创建网格项

- **init(_:spacing:alignment:)**：以指定的大小、间距和对齐方式创建网格项。

## 检查网格项属性

- **alignment**：放置每个视图时使用的对齐方式。
- **spacing**：到下一个项目的间距。
- **size**：项目的大小，即列项目的宽度或行项目的高度。
- **GridItem.Size**：网格布局中一行或多行或多列的小轴尺寸。

## 动态排列二维视图

- **LazyHGrid**：一种容器视图，可将其子视图安排在一个水平增长的网格中，只在需要时创建项目。
- **LazyVGrid**：一种容器视图，它将其子视图排列在一个垂直增长的网格中，只在需要时创建项目。

## 符合

- 可复制
- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/GridItem
crawled: 2025-12-02T17:38:11Z
---

# GridItem

**Structure**

A description of a row or a column in a lazy grid.

## Declaration

```swift
struct GridItem
```

## Overview

Use an array of `GridItem` instances to configure the layout of items in a lazy grid. Each grid item in the array specifies layout properties like size and spacing for the rows of a [LazyHGrid](LazyHGrid.zh-Hans.md) or the columns of a [LazyVGrid](LazyVGrid.zh-Hans.md). The following example defines four rows for a horizontal grid, each with different characteristics:

```swift
struct GridItemDemo: View {
    let rows = [
        GridItem(.fixed(30), spacing: 1),
        GridItem(.fixed(60), spacing: 10),
        GridItem(.fixed(90), spacing: 20),
        GridItem(.fixed(10), spacing: 50)
    ]

    var body: some View {
        ScrollView(.horizontal) {
            LazyHGrid(rows: rows, spacing: 5) {
                ForEach(0...300, id: \.self) { _ in
                    Color.red.frame(width: 30)
                    Color.green.frame(width: 30)
                    Color.blue.frame(width: 30)
                    Color.yellow.frame(width: 30)
                }
            }
        }
    }
}
```

A lazy horizontal grid sets the width of each column based on the widest cell in the column. It can do this because it has access to all of the views in a given column at once. In the example above, the [Color](Color.zh-Hans.md) views always have the same fixed width, resulting in a uniform column width across the whole grid.

However, a lazy horizontal grid doesn’t generally have access to all the views in a row, because it generates new cells as people scroll through information in your app. Instead, it relies on a grid item for information about each row. The example above indicates a different fixed height for each row, and sets a different amount of spacing to appear after each row:



## Creating a grid item

- **init(_:spacing:alignment:)**: Creates a grid item with the specified size, spacing, and alignment.

## Inspecting grid item properties

- **alignment**: The alignment to use when placing each view.
- **spacing**: The spacing to the next item.
- **size**: The size of the item, which is the width of a column item or the height of a row item.
- **GridItem.Size**: The size in the minor axis of one or more rows or columns in a grid layout.

## Dynamically arranging views in two dimensions

- **LazyHGrid**: A container view that arranges its child views in a grid that grows horizontally, creating items only as needed.
- **LazyVGrid**: A container view that arranges its child views in a grid that grows vertically, creating items only as needed.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype

