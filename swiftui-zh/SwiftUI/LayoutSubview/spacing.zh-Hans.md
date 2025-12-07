---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubview/spacing
抓取时间： 2025-12-02T20:59:10Z
---

# 间距

**实例属性**

子视图的首选间距值。

## 声明

```swift
var spacing: ViewSpacing { get }
```

## 讨论

此[ViewSpacing](../ViewSpacing.zh-Hans.md) 实例表示自定义布局中的子视图希望与下一个视图之间有多大的空间。它包含对所有边缘的偏好，并可能考虑到本视图和相邻视图的类型。如果您的[Layout](../Layout.zh-Hans.md) 类型根据间距偏好来放置子视图，则可使用此实例来计算此子视图与下一视图之间的距离。有关示例，请参阅[placeSubviews(in:proposal:subviews:cache:)](../Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md)。

您还可以将此实例与其他子视图的实例合并，以构建一个适合子视图容器的新实例。请参见 [spacing(subviews:cache:)](../Layout/spacing_subviews_cache.zh-Hans.md)。

## 获取子视图特征

- **dimensions(in:)**：询问子视图的尺寸和对齐方式。
- **sizeThatFits(_:)**：询问子视图的尺寸。
- **priority**：询问子视图的尺寸：子视图的布局优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview/spacing
crawled: 2025-12-02T20:59:10Z
---

# spacing

**Instance Property**

The subviews’s preferred spacing values.

## Declaration

```swift
var spacing: ViewSpacing { get }
```

## Discussion

This [ViewSpacing](../ViewSpacing.zh-Hans.md) instance indicates how much space a subview in a custom layout prefers to have between it and the next view. It contains preferences for all edges, and might take into account the type of both this and the adjacent view. If your [Layout](../Layout.zh-Hans.md) type places subviews based on spacing preferences, use this instance to compute a distance between this subview and the next. See [placeSubviews(in:proposal:subviews:cache:)](../Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) for an example.

You can also merge this instance with instances from other subviews to construct a new instance that’s suitable for the subviews’ container. See [spacing(subviews:cache:)](../Layout/spacing_subviews_cache.zh-Hans.md).

## Getting subview characteristics

- **dimensions(in:)**: Asks the subview for its dimensions and alignment guides.
- **sizeThatFits(_:)**: Asks the subview for its size.
- **priority**: The layout priority of the subview.

