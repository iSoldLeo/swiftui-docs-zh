---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior/viewAligned
抓取时间： 2025-12-03T06:42:11Z
---

# viewAligned

**类型属性**

使滚动目标与基于视图的几何体对齐的滚动行为。

## 声明

```swift
static var viewAligned: ViewAlignedScrollTargetBehavior { get }
```

## 讨论

当滚动视图应始终将其滚动目标对齐到与视图几何图形对齐的矩形时，就可以使用此行为。在下面的示例中，滚动视图总是选择一个项目视图来对齐。

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 10.0) {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollTargetBehavior(.viewAligned)
.padding(.horizontal, 20.0)
```

您可以使用`View/scrollTargetLayout()`修改器来配置哪些视图应用于结算。将此修改器应用于 [LazyVStack](../LazyVStack.zh-Hans.md) 或 [HStack](../HStack.zh-Hans.md) 等布局容器，该布局中的每个视图都将被考虑进行对齐。

您可以使用`ViewAlignedScrollTargetBehavior.LimitBehavior` 类型自定义视图对齐行为是否限制一次可滚动的视图数量。如果提供`ViewAlignedScrollTargetBehavior.LimitBehavior/always` 值，则该行为始终只允许同时滚动几个视图。

默认情况下，视图对齐行为会限制在紧凑型水平尺寸类中可在水平轴上滚动的视图数量，以及在紧凑型垂直尺寸类中可在垂直轴上滚动的视图数量，除此之外不会对可滚动的视图数量施加任何限制。

## 获取滚动目标行为

- **paging**：将滚动目标与基于容器的几何体对齐的滚动行为。
- **viewAligned(limitBehavior:)**：使滚动目标与基于视图的几何体对齐的滚动行为。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior/viewAligned
crawled: 2025-12-03T06:42:11Z
---

# viewAligned

**Type Property**

The scroll behavior that aligns scroll targets to view-based geometry.

## Declaration

```swift
static var viewAligned: ViewAlignedScrollTargetBehavior { get }
```

## Discussion

You use this behavior when a scroll view should always align its scroll targets to a rectangle that’s aligned to the geometry of a view. In the following example, the scroll view always picks an item view to settle on.

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 10.0) {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollTargetBehavior(.viewAligned)
.padding(.horizontal, 20.0)
```

You configure which views should be used for settling using the `View/scrollTargetLayout()` modifier. Apply this modifier to a layout container like [LazyVStack](../LazyVStack.zh-Hans.md) or [HStack](../HStack.zh-Hans.md) and each individual view in that layout will be considered for alignment.

You can customize whether the view aligned behavior limits the number of views that can be scrolled at a time by using the `ViewAlignedScrollTargetBehavior.LimitBehavior` type. Provide a value of `ViewAlignedScrollTargetBehavior.LimitBehavior/always` to always have the behavior only allow a few views to be scrolled at a time.

By default, the view aligned behavior limits the number of views it scrolls when in a compact horizontal size class when scrollable in the horizontal axis, when in a compact vertical size class when scrollable in the vertical axis, and otherwise doesn’t impose any limit on the number of views that can be scrolled.

## Getting the scroll target behavior

- **paging**: The scroll behavior that aligns scroll targets to container-based geometry.
- **viewAligned(limitBehavior:)**: The scroll behavior that aligns scroll targets to view-based geometry.

