--- 来源：https://developer.apple.com/documentation/SwiftUI/LazyVGrid/init(columns:alignment:spacing:pinnedViews:content:)

抓取时间：2025-12-01T10:31:41Z

---

# init(columns:alignment:spacing:pinnedViews:content:)

**Initializer**

创建一个垂直扩展的网格。

## 声明

```swift
init(columns: [GridItem], alignment: HorizontalAlignment = .center, spacing: CGFloat? = nil, pinnedViews: PinnedScrollableViews = .init(), @ViewBuilder content: () -> Content)
```

## 参数

- **columns**：用于设置网格每行大小和位置的网格项数组。

- **alignment**：网格在其父视图中的对齐方式。

- **spacing**：网格与其父视图中下一个网格项之间的间距。

- **pinnedViews**：要固定到父滚动视图边界的视图。

- **content**：网格的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/LazyVGrid/init(columns:alignment:spacing:pinnedViews:content:)
crawled: 2025-12-01T10:31:41Z
---

# init(columns:alignment:spacing:pinnedViews:content:)

**Initializer**

Creates a grid that grows vertically.

## Declaration

```swift
init(columns: [GridItem], alignment: HorizontalAlignment = .center, spacing: CGFloat? = nil, pinnedViews: PinnedScrollableViews = .init(), @ViewBuilder content: () -> Content)
```

## Parameters

- **columns**: An array of grid items to size and position each row of the grid.
- **alignment**: The alignment of the grid within its parent view.
- **spacing**: The spacing between the grid and the next item in its parent view.
- **pinnedViews**: Views to pin to the bounds of a parent scroll view.
- **content**: The content of the grid.

