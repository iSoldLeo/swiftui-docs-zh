---
来源：https://developer.apple.com/documentation/SwiftUI/Layout/placeSubviews(in:proposal:subviews:cache:)
抓取时间： 2025-11-30T21:37:50Z
---

# placeSubviews(in:proposal:subviews:cache:)

**实例方法**

为布局的每个子视图指定位置。

## 声明

```swift
func placeSubviews(in bounds: CGRect, proposal: ProposedViewSize, subviews: Self.Subviews, cache: inout Self.Cache)
```

## 参数

- **bounds**：容器视图的父视图分配给容器视图的区域，在父视图的坐标空间中指定。容器的所有子视图都放置在该区域内。该区域的大小与容器先前调用[sizeThatFits(proposal:subviews:cache:)](sizeThatFits_proposal_subviews_cache.zh-Hans.md) 方法返回的大小相匹配。
- **proposal**：尺寸提案，容器从中生成父代用于创建`bounds` 参数的尺寸。父节点在调用放置方法之前可能会提出多个尺寸建议，但在放置容器时，它总是使用其中一个建议和相应的返回尺寸。
- **subviews**：表示容器排列的视图的代理集合。使用集合中的代理可以获取有关子视图的信息，并告诉子视图在哪里出现。
- **cache**：计算数据的可选存储空间，可在自定义布局容器的方法之间共享。详见 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md)。

## 讨论

SwiftUI 调用此方法的实现来告诉您的自定义布局容器放置其子视图。通过此方法，在 `subviews` 中的每个元素上调用 [place(at:anchor:proposal:)](../LayoutSubview/place_at_anchor_proposal.zh-Hans.md) 方法，以告诉子视图在用户界面中的位置。

例如，您可以创建一个基本的垂直堆栈，将视图放置在一列中，视图在其前缘水平对齐：

```swift
struct BasicVStack: Layout {
    func placeSubviews(
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) {
        var point = bounds.origin
        for subview in subviews {
            subview.place(at: point, anchor: .topLeading, proposal: .unspecified)
            point.y += subview.dimensions(in: .unspecified).height
        }
    }

    // This layout also needs a sizeThatFits() implementation.
}
```

该示例创建了一个放置点，该点从指定的 `bounds` 输入的原点开始，并以此放置第一个子视图。然后，它会按照子视图的高度在 y 维度上移动该点，并使用[dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) 方法读取高度。这样就为循环的下一次迭代做好了准备。所有的子视图操作都会使用[unspecified](../ProposedViewSize/unspecified.zh-Hans.md)尺寸建议来指示子视图应该使用并报告其理想尺寸。

更复杂的布局容器可能会根据子视图的[spacing](../LayoutSubview/spacing.zh-Hans.md) 偏好在子视图之间添加空间，或根据输入配置添加固定空间。例如，你可以扩展基本垂直堆栈的布局方法，计算相邻子视图之间的首选距离，并将结果存储在数组中：

```swift
let spacing: [CGFloat] = subviews.indices.dropLast().map { index in
    subviews[index].spacing.distance(
        to: subviews[index + 1].spacing,
        along: .vertical)
}
```

间距的[distance(to:along:)](../ViewSpacing/distance_to_along.zh-Hans.md)方法会考虑相邻视图在它们相遇的边缘上的偏好。它会返回满足两个视图对给定边缘偏好的最小距离。例如，如果一个视图在其底边上至少偏好 `2` 个点，而下一个视图在其顶边上至少偏好 `8` 个点，则距离方法会返回 `8`，因为这是满足两个视图偏好的最小值。

更新放置计算，使用间距值：

```swift
var point = bounds.origin
for (index, subview) in subviews.enumerated() {
    if index > 0 { point.y += spacing[index - 1] } // Add spacing.
    subview.place(at: point, anchor: .topLeading, proposal: .unspecified)
    point.y += subview.dimensions(in: .unspecified).height
}
```

请确保在放置过程中使用的计算方法与其他协议方法中针对给定输入集的计算方法一致。例如，如果您在放置过程中增加了间距，请确保您的[sizeThatFits(proposal:subviews:cache:)](sizeThatFits_proposal_subviews_cache.zh-Hans.md) 实现考虑了额外的空间。同样，如果尺寸调整方法对不同的尺寸建议返回不同的值，请确保放置方法以相同的方式响应其 `proposal` 输入。

## 确定容器大小并放置子视图

- **sizeThatFits(proposal:subviews:cache:)**：根据建议的大小和视图的子视图，返回复合视图的大小。
- **Layout.Subviews**：布局视图子视图的代理集合。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/placeSubviews(in:proposal:subviews:cache:)
crawled: 2025-11-30T21:37:50Z
---

# placeSubviews(in:proposal:subviews:cache:)

**Instance Method**

Assigns positions to each of the layout’s subviews.

## Declaration

```swift
func placeSubviews(in bounds: CGRect, proposal: ProposedViewSize, subviews: Self.Subviews, cache: inout Self.Cache)
```

## Parameters

- **bounds**: The region that the container view’s parent allocates to the container view, specified in the parent’s coordinate space. Place all the container’s subviews within the region. The size of this region matches a size that your container previously returned from a call to the [sizeThatFits(proposal:subviews:cache:)](sizeThatFits_proposal_subviews_cache.zh-Hans.md) method.
- **proposal**: The size proposal from which the container generated the size that the parent used to create the `bounds` parameter. The parent might propose more than one size before calling the placement method, but it always uses one of the proposals and the corresponding returned size when placing the container.
- **subviews**: A collection of proxies that represent the views that the container arranges. Use the proxies in the collection to get information about the subviews and to tell the subviews where to appear.
- **cache**: Optional storage for calculated data that you can share among the methods of your custom layout container. See [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) for details.

## Discussion

SwiftUI calls your implementation of this method to tell your custom layout container to place its subviews. From this method, call the [place(at:anchor:proposal:)](../LayoutSubview/place_at_anchor_proposal.zh-Hans.md) method on each element in `subviews` to tell the subviews where to appear in the user interface.

For example, you can create a basic vertical stack that places views in a column, with views horizontally aligned on their leading edge:

```swift
struct BasicVStack: Layout {
    func placeSubviews(
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) {
        var point = bounds.origin
        for subview in subviews {
            subview.place(at: point, anchor: .topLeading, proposal: .unspecified)
            point.y += subview.dimensions(in: .unspecified).height
        }
    }

    // This layout also needs a sizeThatFits() implementation.
}
```

The example creates a placement point that starts at the origin of the specified `bounds` input and uses that to place the first subview. It then moves the point in the y dimension by the subview’s height, which it reads using the [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) method. This prepares the point for the next iteration of the loop. All subview operations use an [unspecified](../ProposedViewSize/unspecified.zh-Hans.md) size proposal to indicate that subviews should use and report their ideal size.

A more complex layout container might add space between subviews according to their [spacing](../LayoutSubview/spacing.zh-Hans.md) preferences, or a fixed space based on input configuration. For example, you can extend the basic vertical stack’s placement method to calculate the preferred distances between adjacent subviews and store the results in an array:

```swift
let spacing: [CGFloat] = subviews.indices.dropLast().map { index in
    subviews[index].spacing.distance(
        to: subviews[index + 1].spacing,
        along: .vertical)
}
```

The spacing’s [distance(to:along:)](../ViewSpacing/distance_to_along.zh-Hans.md) method considers the preferences of adjacent views on the edge where they meet. It returns the smallest distance that satisfies both views’ preferences for the given edge. For example, if one view prefers at least `2` points on its bottom edge, and the next view prefers at least `8` points on its top edge, the distance method returns `8`, because that’s the smallest value that satisfies both preferences.

Update the placement calculations to use the spacing values:

```swift
var point = bounds.origin
for (index, subview) in subviews.enumerated() {
    if index > 0 { point.y += spacing[index - 1] } // Add spacing.
    subview.place(at: point, anchor: .topLeading, proposal: .unspecified)
    point.y += subview.dimensions(in: .unspecified).height
}
```

Be sure that you use computations during placement that are consistent with those in your implementation of other protocol methods for a given set of inputs. For example, if you add spacing during placement, make sure your implementation of [sizeThatFits(proposal:subviews:cache:)](sizeThatFits_proposal_subviews_cache.zh-Hans.md) accounts for the extra space. Similarly, if the sizing method returns different values for different size proposals, make sure the placement method responds to its `proposal` input in the same way.

## Sizing the container and placing subviews

- **sizeThatFits(proposal:subviews:cache:)**: Returns the size of the composite view, given a proposed size and the view’s subviews.
- **Layout.Subviews**: A collection of proxies for the subviews of a layout view.

