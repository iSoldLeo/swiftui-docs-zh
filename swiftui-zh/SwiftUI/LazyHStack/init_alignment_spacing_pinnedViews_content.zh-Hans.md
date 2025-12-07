---
来源：https://developer.apple.com/documentation/SwiftUI/LazyHStack/init(对齐方式:间距:pinnedViews:内容:)
抓取时间： 2025-12-01T10:31:40Z
---

# init(alignment:spacing:pinnedViews:content:)

**Initializer**

使用给定的间距、垂直对齐方式、钉扎行为和内容创建懒惰水平堆栈视图。

### 声明

```swift
init(alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, pinnedViews: PinnedScrollableViews = .init(), @ViewBuilder content: () -> Content)
```

## 参数

- **alignment**：用于对齐该堆栈中子视图的指南。所有子视图的垂直屏幕坐标相同。
- **spacing**：相邻子视图之间的距离，如果希望堆栈为每对子视图选择默认距离，则输入 `nil`。
- **pinnedViews**：将被固定的子视图的类型。
- **content**：创建此堆栈内容的视图生成器。


---
source: https://developer.apple.com/documentation/SwiftUI/LazyHStack/init(alignment:spacing:pinnedViews:content:)
crawled: 2025-12-01T10:31:40Z
---

# init(alignment:spacing:pinnedViews:content:)

**Initializer**

Creates a lazy horizontal stack view with the given spacing, vertical alignment, pinning behavior, and content.

## Declaration

```swift
init(alignment: VerticalAlignment = .center, spacing: CGFloat? = nil, pinnedViews: PinnedScrollableViews = .init(), @ViewBuilder content: () -> Content)
```

## Parameters

- **alignment**: The guide for aligning the subviews in this stack. All child views have the same vertical screen coordinate.
- **spacing**: The distance between adjacent subviews, or `nil` if you want the stack to choose a default distance for each pair of subviews.
- **pinnedViews**: The kinds of child views that will be pinned.
- **content**: A view builder that creates the content of this stack.

