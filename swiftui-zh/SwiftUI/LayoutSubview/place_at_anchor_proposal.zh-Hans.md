---
来源：https://developer.apple.com/documentation/SwiftUI/LayoutSubview/place(at:anchor:proposal:)
抓取时间：2025-12-02T20:59:08Z
---

# place(at:anchor:proposal:)

**实例方法**

为子视图指定位置和建议尺寸。

## 声明

```swift
func place(at position: CGPoint, anchor: UnitPoint = .topLeading, proposal: ProposedViewSize)
```

## 参数

- **position**：子视图的锚点在容器视图中相对于容器边界的位置。
- **anchor**：子视图上出现在 `position` 处的单位点。您可以使用内置点，如 [center](../UnitPoint/center.zh-Hans.md)，也可以创建自定义[UnitPoint](../UnitPoint.zh-Hans.md)。
- **proposal**：建议的子视图大小。在 SwiftUI 中，视图可自行选择大小，但在选择时可以考虑父视图的建议大小。

### 讨论

在实现[Layout](../Layout.zh-Hans.md) 协议的[placeSubviews(in:proposal:subviews:cache:)](../Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 方法时，为布局排列的每个子视图调用此方法。提供子视图在容器边界内应出现的位置，以及指示子视图的哪一部分出现在该点的锚点。

包含建议的大小，以便子视图在调整自身大小时加以考虑。要在调用此方法之前了解特定建议的子视图大小，可以在具有相同建议的子视图上调用 [dimensions(in:)](dimensions_in.zh-Hans.md) 或 [sizeThatFits(_:)](sizeThatFits.zh-Hans.md) 方法。这样就可以在确定子视图位置之前了解子视图的大小。



如果对一个子视图多次调用此方法，则以最后一次调用为准。如果不为子视图调用此方法，子视图将显示在其布局容器的中心，并使用布局容器的尺寸建议。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview/place(at:anchor:proposal:)
crawled: 2025-12-02T20:59:08Z
---

# place(at:anchor:proposal:)

**Instance Method**

Assigns a position and proposed size to the subview.

## Declaration

```swift
func place(at position: CGPoint, anchor: UnitPoint = .topLeading, proposal: ProposedViewSize)
```

## Parameters

- **position**: The place where the anchor of the subview should appear in its container view, relative to container’s bounds.
- **anchor**: The unit point on the subview that appears at `position`. You can use a built-in point, like [center](../UnitPoint/center.zh-Hans.md), or you can create a custom [UnitPoint](../UnitPoint.zh-Hans.md).
- **proposal**: A proposed size for the subview. In SwiftUI, views choose their own size, but can take a size proposal from their parent view into account when doing so.

## Discussion

Call this method from your implementation of the [Layout](../Layout.zh-Hans.md) protocol’s [placeSubviews(in:proposal:subviews:cache:)](../Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) method for each subview arranged by the layout. Provide a position within the container’s bounds where the subview should appear, and an anchor that indicates which part of the subview appears at that point.

Include a proposed size that the subview can take into account when sizing itself. To learn the subview’s size for a given proposal before calling this method, you can call the [dimensions(in:)](dimensions_in.zh-Hans.md) or [sizeThatFits(_:)](sizeThatFits.zh-Hans.md) method on the subview with the same proposal. That enables you to know subview sizes before committing to subview positions.



If you call this method more than once for a subview, the last call takes precedence. If you don’t call this method for a subview, the subview appears at the center of its layout container and uses the layout container’s size proposal.

