---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior/paging
抓取时间： 2025-12-03T06:42:10Z
---

# 分页

**类型属性**

将滚动目标与基于容器的几何体对齐的滚动行为。

## 声明

```swift
static var paging: PagingScrollTargetBehavior { get }
```

## 讨论

在下面的示例中，懒人堆栈中的每个视图在两个方向上都是灵活的，滚动视图会固定在容器对齐的边界上。

```swift
ScrollView {
    LazyVStack(spacing: 0.0) {
        ForEach(items) { item in
            FullScreenItem(item)
        }
    }
}
.scrollTargetBehavior(.paging)
```

## 获取滚动目标行为

- **viewAligned**：使滚动目标与基于视图的几何体对齐的滚动行为。
- **viewAligned(limitBehavior:)**：使滚动目标与基于视图的几何体对齐的滚动行为。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior/paging
crawled: 2025-12-03T06:42:10Z
---

# paging

**Type Property**

The scroll behavior that aligns scroll targets to container-based geometry.

## Declaration

```swift
static var paging: PagingScrollTargetBehavior { get }
```

## Discussion

In the following example, every view in the lazy stack is flexible in both directions and the scroll view settles to container-aligned boundaries.

```swift
ScrollView {
    LazyVStack(spacing: 0.0) {
        ForEach(items) { item in
            FullScreenItem(item)
        }
    }
}
.scrollTargetBehavior(.paging)
```

## Getting the scroll target behavior

- **viewAligned**: The scroll behavior that aligns scroll targets to view-based geometry.
- **viewAligned(limitBehavior:)**: The scroll behavior that aligns scroll targets to view-based geometry.

