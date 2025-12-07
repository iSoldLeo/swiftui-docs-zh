--- 来源：https://developer.apple.com/documentation/SwiftUI/composing-custom-layouts-with-swiftui

抓取时间：2025-12-02T15:50:57Z

---

# 使用 SwiftUI 构建自定义布局

**示例代码**

使用 SwiftUI 提供的布局工具，在应用界面中排列视图。

## 概述

此示例应用演示了 SwiftUI 提供的许多布局工具，构建了一个允许用户投票选出自己最喜欢的宠物类型的界面。该应用提供按钮供用户选择特定的宠物类型，并在排行榜上显示各个候选宠物的得票数和相对排名。它还显示了宠物的头像，并根据当前的排名进行排列。

### 使用网格在二维空间中排列视图

为了在显示屏中央绘制显示投票数和百分比的排行榜，示例使用了 [Grid](Grid.zh-Hans.md) 视图。

网格包含一个 [GridRow](GridRow.zh-Hans.md)，该视图位于 [ForEach](ForEach.zh-Hans.md) 内部，其中行中的每个视图都会创建一个列单元格。因此，第一个视图出现在第一列，第二个视图出现在第二列，依此类推。由于 [Divider](Divider.zh-Hans.md) 出现在网格行实例之外，因此它创建的行跨越了网格的宽度。

```swift
Grid(alignment: .leading) {
    ForEach(model.pets) { pet in
        GridRow {
            Text(pet.type)
            ProgressView(
                value: Double(pet.votes),
                total: Double(max(1, model.totalVotes))) // Avoid dividing by zero.
            Text("\(pet.votes)")
                .gridColumnAlignment(.trailing)
        }

        Divider()
    }
}
```

示例使用前缘对齐初始化网格，该对齐方式应用于网格中的每个单元格。同时，出现在投票数单元格上的 [gridColumnAlignment(_:)](View/gridColumnAlignment.zh-Hans.md) 视图修饰符会覆盖该列中单元格的对齐方式，使其使用后缘对齐。

### 创建自定义等宽布局

该应用在界面底部提供投票按钮。

为了确保所有按钮宽度相同，且不超过按钮文本最宽处，该应用创建了一个符合 [Layout](Layout.zh-Hans.md) 协议的自定义布局容器类型。等宽水平堆栈 (`MyEqualWidthHStack`) 会测量所有子视图的理想尺寸，并为每个子视图提供最宽的理想尺寸。

该自定义堆栈实现了协议的两个必需方法。首先，[sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) 会根据一组子视图报告容器的尺寸。

```swift
func sizeThatFits(
    proposal: ProposedViewSize,
    subviews: Subviews,
    cache: inout Void
) -> CGSize {
    guard !subviews.isEmpty else { return .zero }

    let maxSize = maxSize(subviews: subviews)
    let spacing = spacing(subviews: subviews)
    let totalSpacing = spacing.reduce(0) { $0 + $1 }

    return CGSize(
        width: maxSize.width * CGFloat(subviews.count) + totalSpacing,
        height: maxSize.height)
}
```

此方法将每个维度上的最大尺寸与子视图之间的水平间距相结合，以计算容器的总尺寸。然后，[placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 会告知每个子视图在布局边界内的具体位置。

```swift
func placeSubviews(
    in bounds: CGRect,
    proposal: ProposedViewSize,
    subviews: Subviews,
    cache: inout Void
) {
    guard !subviews.isEmpty else { return }

    let maxSize = maxSize(subviews: subviews)
    let spacing = spacing(subviews: subviews)

    let placementProposal = ProposedViewSize(width: maxSize.width, height: maxSize.height)
    var nextX = bounds.minX + maxSize.width / 2

    for index in subviews.indices {
        subviews[index].place(
            at: CGPoint(x: nextX, y: bounds.midY),
            anchor: .center,
            proposal: placementProposal)
        nextX += maxSize.width + spacing[index]
    }
}
```

该方法为子视图创建一个统一的尺寸建议，然后结合每个子视图中不同的点，将按钮以默认间距水平排列。

### 选择合适的视图

投票按钮的大小取决于其包含的文本宽度。对于使用其他语言或较大字号的用户，水平排列的按钮可能无法完整显示在屏幕上。因此，应用使用 [ViewThatFits](ViewThatFits.zh-Hans.md) 让 SwiftUI 在水平和垂直排列按钮之间进行选择，以适应可用空间。

```swift
ViewThatFits { // Choose the first view that fits.
    MyEqualWidthHStack { // Arrange horizontally if it fits...
        Buttons()
    }
    MyEqualWidthVStack { // ...or vertically, otherwise.
        Buttons()
    }
}
```

为了确保按钮在垂直排列时保持等宽，应用使用了一个自定义的等宽垂直堆叠（`MyEqualWidthVStack`），其与水平版本非常相似。

### 使用缓存提升布局效率

[Layout](Layout.zh-Hans.md) 协议的方法接受一个双向 `cache` 参数。缓存提供对可选存储的访问，该存储可在特定布局实例的所有方法之间共享。为了演示缓存的用法，示例应用程序的等宽垂直布局创建了一个存储，用于在其 [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) 和 [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 实现之间共享尺寸和间距计算。

首先，布局定义了一个 `CacheData` 类型的存储。

```swift
struct CacheData {
    let maxSize: CGSize
    let spacing: [CGFloat]
    let totalSpacing: CGFloat
}
```

然后，它实现了协议的可选 [makeCache(subviews:)](Layout/makeCache_subviews.zh-Hans.md) 方法，以对一组子视图进行计算，并返回上述定义的类型的值。

```swift
func makeCache(subviews: Subviews) -> CacheData {
    let maxSize = maxSize(subviews: subviews)
    let spacing = spacing(subviews: subviews)
    let totalSpacing = spacing.reduce(0) { $0 + $1 }

    return CacheData(
        maxSize: maxSize,
        spacing: spacing,
        totalSpacing: totalSpacing)
}
```

如果子视图发生变化，SwiftUI 会调用布局的 [updateCache(_:subviews:)](Layout/updateCache___subviews.zh-Hans.md) 方法。该方法的默认实现会再次调用 [makeCache(subviews:)](Layout/makeCache_subviews.zh-Hans.md) 方法，重新计算数据。然后，`sizeThatFits(proposal:subviews:cache:)` 和 `placeSubviews(in:proposal:subviews:cache:)` 方法会使用它们的 `cache` 参数来检索数据。例如，`placeSubviews(in:proposal:subviews:cache:)` 方法会从缓存中读取尺寸和间距数组。

```swift
let maxSize = cache.maxSize
let spacing = cache.spacing
```

与此形成对比的是等宽水平堆栈，它不使用缓存，而是每次需要尺寸和间距信息时都重新计算。

### 创建带偏移的自定义径向布局

为了将宠物头像以圆形显示，应用定义了一个径向布局 (`MyRadialLayout`)。

与其他自定义布局一样，此布局需要两个必需的方法。对于 [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md)，布局会返回容器建议的尺寸来填充可用空间。

```swift
proposal.replacingUnspecifiedDimensions()
```

应用使用建议的 [replacingUnspecifiedDimensions(by:)](ProposedViewSize/replacingUnspecifiedDimensions_by.zh-Hans.md) 方法将建议转换为具体的尺寸。然后，为了放置子视图，布局会旋转一个向量，将该向量平移到放置区域的中心，并以此作为子视图的锚点。

```swift
for (index, subview) in subviews.enumerated() {
    // Find a vector with an appropriate size and rotation.
    var point = CGPoint(x: 0, y: -radius)
        .applying(CGAffineTransform(
            rotationAngle: angle * Double(index) + offset))

    // Shift the vector to the middle of the region.
    point.x += bounds.midX
    point.y += bounds.midY

    // Place the subview.
    subview.place(at: point, anchor: .center, proposal: .unspecified)
}
```

应用应用于旋转的偏移量会考虑当前的排名，将排名较高的宠物放置在界面顶部附近。该应用使用 [LayoutValueKey](LayoutValueKey.zh-Hans.md) 协议将排名存储在子视图中，然后在放置视图之前读取这些值以计算偏移量。

### 布局间过渡动画

径向布局可以计算出一个偏移量，为除一组排名之外的所有排名创建合适的排列：无法在头像呈圆形排列的情况下显示三个并列排名。为了解决这个问题，应用会检测到这种情况，并使用 [HStackLayout](HStackLayout.zh-Hans.md) 类型将头像排列成一行。[HStackLayout](HStackLayout.zh-Hans.md) 类型是内置 [HStack](HStack.zh-Hans.md) 类型的一个版本，符合 [Layout](Layout.zh-Hans.md) 协议。为了在这些布局类型之间进行过渡，应用使用 [AnyLayout](AnyLayout.zh-Hans.md) 类型。

```swift
let layout = model.isAllWayTie ? AnyLayout(HStackLayout()) : AnyLayout(MyRadialLayout())

Podium()
    .overlay(alignment: .top) {
        layout {
            ForEach(model.pets) { pet in
                Avatar(pet: pet)
                    .rank(model.rank(pet))
            }
        }
        .animation(.default, value: model.pets)
    }
```

由于视图的结构标识始终保持不变，[animation(_:value:)](View/animation___value.zh-Hans.md) 视图修饰符会在布局类型之间创建动画过渡效果。该修饰符还会为排名变化引起的径向布局变化添加动画效果，因为计算出的偏移量依赖于相同的宠物数据。

### 构建应用文档

要查看有关此应用定义的符号的更多信息，您可以构建应用的文档。在 Xcode 中打开项目，然后选择“产品”>“构建文档”。

有关如何在您自己的应用中包含文档的信息，请参阅 [https://www.swift.org/documentation/docc]。

## 创建自定义布局容器

- **Layout**：定义视图集合几何形状的类型。

- **LayoutSubview**：表示布局中一个子视图的代理。

- **LayoutSubviews**：一组代理值，代表布局视图的子视图。


---
source: https://developer.apple.com/documentation/SwiftUI/composing-custom-layouts-with-swiftui
crawled: 2025-12-02T15:50:57Z
---

# Composing custom layouts with SwiftUI

**Sample Code**

Arrange views in your app’s interface using layout tools that SwiftUI provides.

## Overview

This sample app demonstrates many of the layout tools that SwiftUI provides by building an interface that enables people to vote for their favorite kind of pet. The app offers buttons to vote for a specific pet type, and displays the vote counts and relative rankings of the various contenders on a leaderboard. It also shows avatars for the pets, arranged in a way that reflects the current rankings.





### Arrange views in two dimensions with a grid

To draw a leaderboard in the middle of the display that shows vote counts and percentages, the sample uses a [Grid](Grid.zh-Hans.md) view.



The grid contains a [GridRow](GridRow.zh-Hans.md) inside a [ForEach](ForEach.zh-Hans.md), where each view in the row creates a column cell. So the first view appears in the first column, the second in the second column, and so on. Because the [Divider](Divider.zh-Hans.md) appears outside of a grid row instance, it creates a row that spans the width of the grid.

```swift
Grid(alignment: .leading) {
    ForEach(model.pets) { pet in
        GridRow {
            Text(pet.type)
            ProgressView(
                value: Double(pet.votes),
                total: Double(max(1, model.totalVotes))) // Avoid dividing by zero.
            Text("\(pet.votes)")
                .gridColumnAlignment(.trailing)
        }

        Divider()
    }
}
```

The sample initializes the grid with leading-edge alignment, which applies to every cell in the grid. Meanwhile, the [gridColumnAlignment(_:)](View/gridColumnAlignment.zh-Hans.md) view modifier that appears on the vote count cell overrides the alignment of cells in that column to use trailing-edge alignment.

### Create a custom equal-width layout

The app offers buttons for voting at the bottom of the interface.



To ensure the buttons all have the same width, but are no wider than the widest button text, the app creates a custom layout container type that conforms to the [Layout](Layout.zh-Hans.md) protocol. The equal-width horizontal stack (`MyEqualWidthHStack`) measures the ideal sizes of all its subviews, and offers the widest ideal size to each subview.

The custom stack implements the protocol’s two required methods. First, [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) reports the container’s size, given a set of subviews.

```swift
func sizeThatFits(
    proposal: ProposedViewSize,
    subviews: Subviews,
    cache: inout Void
) -> CGSize {
    guard !subviews.isEmpty else { return .zero }

    let maxSize = maxSize(subviews: subviews)
    let spacing = spacing(subviews: subviews)
    let totalSpacing = spacing.reduce(0) { $0 + $1 }

    return CGSize(
        width: maxSize.width * CGFloat(subviews.count) + totalSpacing,
        height: maxSize.height)
}
```

This method combines the largest size in each dimension with the horizontal spacing between subviews to find the container’s total size. Then, [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) tells each of the subviews where to appear within the layout’s bounds.

```swift
func placeSubviews(
    in bounds: CGRect,
    proposal: ProposedViewSize,
    subviews: Subviews,
    cache: inout Void
) {
    guard !subviews.isEmpty else { return }

    let maxSize = maxSize(subviews: subviews)
    let spacing = spacing(subviews: subviews)

    let placementProposal = ProposedViewSize(width: maxSize.width, height: maxSize.height)
    var nextX = bounds.minX + maxSize.width / 2

    for index in subviews.indices {
        subviews[index].place(
            at: CGPoint(x: nextX, y: bounds.midY),
            anchor: .center,
            proposal: placementProposal)
        nextX += maxSize.width + spacing[index]
    }
}
```

The method creates a single size proposal for the subviews, and then uses that, along with a point that changes for each subview, to arrange the buttons in a horizontal line with default spacing.

### Choose the view that fits

The size of the voting buttons depends on the width of the text they contain. For people that speak another language or that use a larger text size, the horizontally arranged buttons might not fit in the display. So the app uses [ViewThatFits](ViewThatFits.zh-Hans.md) to let SwiftUI choose between a horizontal and a vertical arrangement of the buttons for the one that fits in the available space.

```swift
ViewThatFits { // Choose the first view that fits.
    MyEqualWidthHStack { // Arrange horizontally if it fits...
        Buttons()
    }
    MyEqualWidthVStack { // ...or vertically, otherwise.
        Buttons()
    }
}
```

To ensure that the buttons maintain their equal-width property when arranged vertically, the app uses a custom equal-width vertical stack (`MyEqualWidthVStack`) that’s very similar to the horizontal version.

### Improve layout efficiency with a cache

The methods of the [Layout](Layout.zh-Hans.md) protocol take a bidirectional `cache` parameter. The cache provides access to optional storage that’s shared among all the methods of a particular layout instance. To demonstrate the use of a cache, the sample app’s equal-width vertical layout creates storage to share size and spacing calculations between its [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) and [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) implementations.

First, the layout defines a `CacheData` type for the storage.

```swift
struct CacheData {
    let maxSize: CGSize
    let spacing: [CGFloat]
    let totalSpacing: CGFloat
}
```

It then implements the protocol’s optional [makeCache(subviews:)](Layout/makeCache_subviews.zh-Hans.md) method to do the calculations for a set of subviews, returning a value of the type defined above.

```swift
func makeCache(subviews: Subviews) -> CacheData {
    let maxSize = maxSize(subviews: subviews)
    let spacing = spacing(subviews: subviews)
    let totalSpacing = spacing.reduce(0) { $0 + $1 }

    return CacheData(
        maxSize: maxSize,
        spacing: spacing,
        totalSpacing: totalSpacing)
}
```

If the subviews change, SwiftUI calls the layout’s [updateCache(_:subviews:)](Layout/updateCache___subviews.zh-Hans.md) method. The default implementation of that method calls [makeCache(subviews:)](Layout/makeCache_subviews.zh-Hans.md) again, which recalculates the data. Then the `sizeThatFits(proposal:subviews:cache:)` and `placeSubviews(in:proposal:subviews:cache:)` methods make use of their `cache` parameter to retrieve the data. For example, `placeSubviews(in:proposal:subviews:cache:)` reads the size and the spacing array from the cache.

```swift
let maxSize = cache.maxSize
let spacing = cache.spacing
```

Contrast this with the equal-width horizontal stack, which doesn’t use a cache, and instead calculates the size and spacing information every time it needs that information.



### Create a custom radial layout with an offset

To display the pet avatars in a circle, the app defines a radial layout (`MyRadialLayout`).



Like other custom layouts, this layout needs the two required methods. For [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md), the layout fills the available space by returning whatever size its container proposes.

```swift
proposal.replacingUnspecifiedDimensions()
```

The app uses the proposal’s [replacingUnspecifiedDimensions(by:)](ProposedViewSize/replacingUnspecifiedDimensions_by.zh-Hans.md) method to convert the proposal into a concrete size. Then, to place subviews, the layout rotates a vector, translates the vector to the middle of the placement region, and uses that as the anchor for the subview.

```swift
for (index, subview) in subviews.enumerated() {
    // Find a vector with an appropriate size and rotation.
    var point = CGPoint(x: 0, y: -radius)
        .applying(CGAffineTransform(
            rotationAngle: angle * Double(index) + offset))

    // Shift the vector to the middle of the region.
    point.x += bounds.midX
    point.y += bounds.midY

    // Place the subview.
    subview.place(at: point, anchor: .center, proposal: .unspecified)
}
```

The offset that the app applies to the rotation accounts for the current rankings, placing higher-ranked pets closer to the top of the interface. The app stores ranks on the subviews using the [LayoutValueKey](LayoutValueKey.zh-Hans.md) protocol, and then reads the values to calculate the offset before placing views.

### Animate transitions between layouts

The radial layout can calculate an offset that creates an appropriate arrangement for all but one set of rankings: there’s no way to show a three-way tie with the avatars in a circle. To resolve this, the app detects this condition, and uses it to put the avatars in a line instead, using a the [HStackLayout](HStackLayout.zh-Hans.md) type, which is a version of the built-in [HStack](HStack.zh-Hans.md) that conforms to the [Layout](Layout.zh-Hans.md) protocol. To transition between these layout types, the app uses the [AnyLayout](AnyLayout.zh-Hans.md) type.

```swift
let layout = model.isAllWayTie ? AnyLayout(HStackLayout()) : AnyLayout(MyRadialLayout())

Podium()
    .overlay(alignment: .top) {
        layout {
            ForEach(model.pets) { pet in
                Avatar(pet: pet)
                    .rank(model.rank(pet))
            }
        }
        .animation(.default, value: model.pets)
    }
```

Because the structural identity of the views remains the same throughout, the [animation(_:value:)](View/animation___value.zh-Hans.md) view modifier creates animated transitions between layout types. The modifier also animates radial layout changes that result from changes in the rankings because the calculated offsets depend on the same pet data.

### Build documentation for the app

To see more information about the symbols defined by this app, you can build the app’s documentation. Open the project in Xcode and select Product > Build Documentation.

For information about how to include documentation in your own apps, see [https://www.swift.org/documentation/docc].

## Creating a custom layout container

- **Layout**: A type that defines the geometry of a collection of views.
- **LayoutSubview**: A proxy that represents one subview of a layout.
- **LayoutSubviews**: A collection of proxy values that represent the subviews of a layout view.

