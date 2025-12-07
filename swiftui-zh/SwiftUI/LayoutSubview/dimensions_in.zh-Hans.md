---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubview/dimensions(in:)
抓取时间：2025-12-02T20:59:09Z
---

# dimensions(in:)

**实例方法**

询问子视图的尺寸和对齐方式。

## 声明

```swift
func dimensions(in proposal: ProposedViewSize) -> ViewDimensions
```

## 参数

- **proposal**：建议的子视图大小。在 SwiftUI 中，视图可以选择自己的大小，但也可以考虑父视图的建议大小。

## 返回值

一个[ViewDimensions](../ViewDimensions.zh-Hans.md)实例，包含高度和宽度，以及一组对齐指引。

## 讨论

调用此方法可向自定义[Layout](../Layout.zh-Hans.md) 类型的子视图询问其大小和对齐方式属性。您可以在实现该协议的任何方法（如 [placeSubviews(in:proposal:subviews:cache:)](../Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 或 [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md)）时调用该方法，以获取布局计算所需的信息。

调用该方法时，您可以使用`proposal` 参数提出一个尺寸。子视图可以选择自己的尺寸，但可能会将提议的尺寸考虑在内。您可以使用不同的建议多次调用此方法，以了解视图是否灵活。例如，您可以提议

- [zero](../ProposedViewSize/zero.zh-Hans.md)，以获得子视图的最小尺寸。
- [infinity](../ProposedViewSize/infinity.zh-Hans.md)获取子视图的最大尺寸。
- [unspecified](../ProposedViewSize/unspecified.zh-Hans.md) 可获取子视图的理想大小。

如果只需要视图的高度和宽度，可以使用 [sizeThatFits(_:)](sizeThatFits.zh-Hans.md) 方法。

## 获取子视图特征

- **sizeThatFits(_:)**：询问子视图的大小。
- **spacing**：子视图的首选间距值。
- **priority**：子视图的布局优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview/dimensions(in:)
crawled: 2025-12-02T20:59:09Z
---

# dimensions(in:)

**Instance Method**

Asks the subview for its dimensions and alignment guides.

## Declaration

```swift
func dimensions(in proposal: ProposedViewSize) -> ViewDimensions
```

## Parameters

- **proposal**: A proposed size for the subview. In SwiftUI, views choose their own size, but can take a size proposal from their parent view into account when doing so.

## Return Value

A [ViewDimensions](../ViewDimensions.zh-Hans.md) instance that includes a height and width, as well as a set of alignment guides.

## Discussion

Call this method to ask a subview of a custom [Layout](../Layout.zh-Hans.md) type about its size and alignment properties. You can call it from your implementation of any of that protocol’s methods, like [placeSubviews(in:proposal:subviews:cache:)](../Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) or [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md), to get information for your layout calculations.

When you call this method, you propose a size using the `proposal` parameter. The subview can choose its own size, but might take the proposal into account. You can call this method more than once with different proposals to find out if the view is flexible. For example, you can propose:

- [zero](../ProposedViewSize/zero.zh-Hans.md) to get the subview’s minimum size.
- [infinity](../ProposedViewSize/infinity.zh-Hans.md) to get the subview’s maximum size.
- [unspecified](../ProposedViewSize/unspecified.zh-Hans.md) to get the subview’s ideal size.

If you need only the view’s height and width, you can use the [sizeThatFits(_:)](sizeThatFits.zh-Hans.md) method instead.

## Getting subview characteristics

- **sizeThatFits(_:)**: Asks the subview for its size.
- **spacing**: The subviews’s preferred spacing values.
- **priority**: The layout priority of the subview.

