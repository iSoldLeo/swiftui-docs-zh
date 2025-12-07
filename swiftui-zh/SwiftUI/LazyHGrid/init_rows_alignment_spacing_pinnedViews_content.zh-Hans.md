---
来源：https://developer.apple.com/documentation/SwiftUI/LazyHGrid/init(行:对齐方式:间距:pinnedViews:内容:)
抓取时间： 2025-12-03T05:42:31Z


# init(rows:alignment:spacing:pinnedViews:content:)

**Initializer**

创建一个水平增长的网格。

## 声明

```swift
init(rows: [GridItem], alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, pinnedViews: PinnedScrollableViews = .init(), @ViewBuilder content: () -> Content)
```

## 参数

- **rows**：网格项数组，用于确定网格每列的大小和位置。
- **alignment**：网格在其父视图中的对齐方式。
- **spacing**：网格与父视图中下一个项目之间的间距。
- **pinnedViews**：要固定到父滚动视图边界的视图。
- **content**：网格的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/LazyHGrid/init(rows:alignment:spacing:pinnedViews:content:)
crawled: 2025-12-03T05:42:31Z
---

# init(rows:alignment:spacing:pinnedViews:content:)

**Initializer**

Creates a grid that grows horizontally.

## Declaration

```swift
init(rows: [GridItem], alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, pinnedViews: PinnedScrollableViews = .init(), @ViewBuilder content: () -> Content)
```

## Parameters

- **rows**: An array of grid items that size and position each column of the grid.
- **alignment**: The alignment of the grid within its parent view.
- **spacing**: The spacing between the grid and the next item in its parent view.
- **pinnedViews**: Views to pin to the bounds of a parent scroll view.
- **content**: The content of the grid.

