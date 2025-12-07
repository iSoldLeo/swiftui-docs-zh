---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/sizeThatFits(_:)
抓取时间： 2025-12-01T02:32:43Z
---

# sizeThatFits(_:)

**实例方法**

根据建议的尺寸，返回将渲染形状的视图的尺寸。

## 声明

```swift
nonisolated func sizeThatFits(_ proposal: ProposedViewSize) -> CGSize
```

## 参数

- **proposal**：容器的大小建议。

## 返回值

表示形状需要多少空间的大小。

## 讨论

执行此方法可以告诉形状的容器，在给定尺寸建议的情况下，形状需要多少空间来渲染自己。

有关布局系统如何选择视图大小的更多详情，请参阅[sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md)。

## 定义形状的大小和路径

- **path(in:)**：将此形状描述为矩形参照框架内的路径。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/sizeThatFits(_:)
crawled: 2025-12-01T02:32:43Z
---

# sizeThatFits(_:)

**Instance Method**

Returns the size of the view that will render the shape, given a proposed size.

## Declaration

```swift
nonisolated func sizeThatFits(_ proposal: ProposedViewSize) -> CGSize
```

## Parameters

- **proposal**: A size proposal for the container.

## Return Value

A size that indicates how much space the shape needs.

## Discussion

Implement this method to tell the container of the shape how much space the shape needs to render itself, given a size proposal.

See [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) for more details about how the layout system chooses the size of views.

## Defining a shape’s size and path

- **path(in:)**: Describes this shape as a path within a rectangular frame of reference.

