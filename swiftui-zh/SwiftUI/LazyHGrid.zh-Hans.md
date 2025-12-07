---
来源： https://developer.apple.com/documentation/SwiftUI/LazyHGrid
抓取时间： 2025-12-02T17:27:24Z
---

# LazyHGrid

**Structure**

一种容器视图，可将其子视图排列在一个水平增长的网格中，只在需要时创建项目。

## 声明

```swift
struct LazyHGrid<Content> where Content : View
```

## 概览

当您想以二维布局显示大量可水平滚动的视图集合时，可使用懒惰水平网格。提供给网格`content` 闭合的第一个视图将显示在网格前缘列的顶行。其他视图占据网格中的连续单元格，从上到下填满第一列，然后填满第二列，依此类推。列的数量可以无限制地增长，但您可以通过向网格的初始化程序提供相应数量的 [GridItem](GridItem.zh-Hans.md) 实例来指定行的数量。

下面示例中的网格定义了两行，并使用[ForEach](ForEach.zh-Hans.md) 结构为每列中的行重复生成一对[Text](Text.zh-Hans.md) 视图：

```swift
struct HorizontalSmileys: View {
    let rows = [GridItem(.fixed(30)), GridItem(.fixed(30))]

    var body: some View {
        ScrollView(.horizontal) {
            LazyHGrid(rows: rows) {
                ForEach(0x1f600...0x1f679, id: \.self) { value in
                    Text(String(format: "%x", value))
                    Text(emoji(value))
                        .font(.largeTitle)
                }
            }
        }
    }

    private func emoji(_ value: Int) -> String {
        guard let scalar = UnicodeScalar(value) else { return "?" }
        return String(Character(scalar))
    }
}
```

对于网格中的每一列，顶行显示 "Smileys "组中的一个 Unicode 代码点，底行显示其对应的表情符号：



使用[Grid](Grid.zh-Hans.md)容器也能实现类似的布局。懒网格只在 SwiftUI 需要显示时才创建子视图，而常规网格则不同，它会立即创建所有子视图。这样，网格就能更好地支持单元格间距和对齐方式。只有在对应用程序进行剖析后发现，[Grid](Grid.zh-Hans.md) 视图会因为试图同时加载过多视图而表现不佳时，才会使用懒网格。

## 创建水平网格

- **init(rows:alignment:spacing:pinnedViews:content:)**：创建一个水平生长的网格。

## 动态排列二维视图

- **LazyVGrid**：一个容器视图，它将其子视图排列在一个垂直增长的网格中，只在需要时创建项目。
- **GridItem**：对懒网格中某一行或某一列的描述。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/LazyHGrid
crawled: 2025-12-02T17:27:24Z
---

# LazyHGrid

**Structure**

A container view that arranges its child views in a grid that grows horizontally, creating items only as needed.

## Declaration

```swift
struct LazyHGrid<Content> where Content : View
```

## Overview

Use a lazy horizontal grid when you want to display a large, horizontally scrollable collection of views arranged in a two dimensional layout. The first view that you provide to the grid’s `content` closure appears in the top row of the column that’s on the grid’s leading edge. Additional views occupy successive cells in the grid, filling the first column from top to bottom, then the second column, and so on. The number of columns can grow unbounded, but you specify the number of rows by providing a corresponding number of [GridItem](GridItem.zh-Hans.md) instances to the grid’s initializer.

The grid in the following example defines two rows and uses a [ForEach](ForEach.zh-Hans.md) structure to repeatedly generate a pair of [Text](Text.zh-Hans.md) views for the rows in each column:

```swift
struct HorizontalSmileys: View {
    let rows = [GridItem(.fixed(30)), GridItem(.fixed(30))]

    var body: some View {
        ScrollView(.horizontal) {
            LazyHGrid(rows: rows) {
                ForEach(0x1f600...0x1f679, id: \.self) { value in
                    Text(String(format: "%x", value))
                    Text(emoji(value))
                        .font(.largeTitle)
                }
            }
        }
    }

    private func emoji(_ value: Int) -> String {
        guard let scalar = UnicodeScalar(value) else { return "?" }
        return String(Character(scalar))
    }
}
```

For each column in the grid, the top row shows a Unicode code point from the “Smileys” group, and the bottom shows its corresponding emoji:



You can achieve a similar layout using a [Grid](Grid.zh-Hans.md) container. Unlike a lazy grid, which creates child views only when SwiftUI needs to display them, a regular grid creates all of its child views right away. This enables the grid to provide better support for cell spacing and alignment. Only use a lazy grid if profiling your app shows that a [Grid](Grid.zh-Hans.md) view performs poorly because it tries to load too many views at once.

## Creating a horizontal grid

- **init(rows:alignment:spacing:pinnedViews:content:)**: Creates a grid that grows horizontally.

## Dynamically arranging views in two dimensions

- **LazyVGrid**: A container view that arranges its child views in a grid that grows vertically, creating items only as needed.
- **GridItem**: A description of a row or a column in a lazy grid.

## Conforms To

- View

