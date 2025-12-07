---
来源：https://developer.apple.com/documentation/SwiftUI/Layout/sizeThatFits(提案：subviews:cache:)
抓取时间： 2025-11-30T21:37:49Z
---

# sizeThatFits(proposal:subviews:cache:)

**实例方法**

根据提议的大小和视图的子视图，返回复合视图的大小。

## 声明

```swift
func sizeThatFits(proposal: ProposedViewSize, subviews: Self.Subviews, cache: inout Self.Cache) -> CGSize
```

## 参数

- **proposal**：容器的大小建议。调用此方法的容器的父视图可能会多次调用该方法并使用不同的建议，以便在决定使用哪种建议进行放置之前更多地了解容器的灵活性。
- **subviews**：代表容器排列的视图的代理集合。在确定容器需要多少空间来显示子视图时，可以使用集合中的代理来获取有关子视图的信息。
- **cache**：计算数据的可选存储空间，可在自定义布局容器的方法之间共享。详见 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md)。

## 返回值

一个大小，表示容器需要多少空间来排列其子视图。

## 讨论

执行此方法可告诉自定义布局容器的父视图，在给定尺寸建议的情况下，该容器需要为一组子视图提供多少空间。父视图可能会在一次布局传递中多次调用此方法，并使用不同的建议尺寸来测试容器的灵活性，比如使用以下建议：

- [zero](../ProposedViewSize/zero.zh-Hans.md)提议；响应布局的最小尺寸。
- [infinity](../ProposedViewSize/infinity.zh-Hans.md)提案；以布局的最大尺寸响应。
- [unspecified](../ProposedViewSize/unspecified.zh-Hans.md)提议；以布局的理想尺寸作出响应。

父节点也可以选择一次测试一个维度的灵活性。例如，一个水平堆栈可能会提出高度固定、宽度无限的建议，然后再提出高度相同、宽度为零的建议。

下面的示例计算了一个基本垂直堆栈的尺寸，该堆栈将视图放置在一列中，视图之间没有间距：

```swift
private struct BasicVStack: Layout {
    func sizeThatFits(
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) -> CGSize {
        subviews.reduce(CGSize.zero) { result, subview in
            let size = subview.sizeThatFits(.unspecified)
            return CGSize(
                width: max(result.width, size.width),
                height: result.height + size.height)
        }
    }

    // This layout also needs a placeSubviews() implementation.
}
```

实现方法是通过调用[sizeThatFits(_:)](../LayoutSubview/sizeThatFits.zh-Hans.md) 方法，询问每个子视图的理想尺寸，并给出[unspecified](../ProposedViewSize/unspecified.zh-Hans.md) 建议尺寸。然后，它将这些值缩减为一个单一的尺寸，该尺寸代表最大子视图宽度和子视图高度之和。由于此示例并不灵活，因此它忽略了输入的大小建议，并始终为给定的子视图集返回相同的值。

SwiftUI 视图可自行选择大小，因此布局引擎总是将此方法返回的值作为复合视图的实际大小。在构建`bounds` 输入到[placeSubviews(in:proposal:subviews:cache:)](placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 方法时会考虑到该大小。

## 确定容器大小并放置子视图

- **placeSubviews(in:proposal:subviews:cache:)**：为布局的每个子视图指定位置。
- **Layout.Subviews**：布局视图子视图的代理集合。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/sizeThatFits(proposal:subviews:cache:)
crawled: 2025-11-30T21:37:49Z
---

# sizeThatFits(proposal:subviews:cache:)

**Instance Method**

Returns the size of the composite view, given a proposed size and the view’s subviews.

## Declaration

```swift
func sizeThatFits(proposal: ProposedViewSize, subviews: Self.Subviews, cache: inout Self.Cache) -> CGSize
```

## Parameters

- **proposal**: A size proposal for the container. The container’s parent view that calls this method might call the method more than once with different proposals to learn more about the container’s flexibility before deciding which proposal to use for placement.
- **subviews**: A collection of proxies that represent the views that the container arranges. You can use the proxies in the collection to get information about the subviews as you determine how much space the container needs to display them.
- **cache**: Optional storage for calculated data that you can share among the methods of your custom layout container. See [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) for details.

## Return Value

A size that indicates how much space the container needs to arrange its subviews.

## Discussion

Implement this method to tell your custom layout container’s parent view how much space the container needs for a set of subviews, given a size proposal. The parent might call this method more than once during a layout pass with different proposed sizes to test the flexibility of the container, using proposals like:

- The [zero](../ProposedViewSize/zero.zh-Hans.md) proposal; respond with the layout’s minimum size.
- The [infinity](../ProposedViewSize/infinity.zh-Hans.md) proposal; respond with the layout’s maximum size.
- The [unspecified](../ProposedViewSize/unspecified.zh-Hans.md) proposal; respond with the layout’s ideal size.

The parent might also choose to test flexibility in one dimension at a time. For example, a horizontal stack might propose a fixed height and an infinite width, and then the same height with a zero width.

The following example calculates the size for a basic vertical stack that places views in a column, with no spacing between the views:

```swift
private struct BasicVStack: Layout {
    func sizeThatFits(
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) -> CGSize {
        subviews.reduce(CGSize.zero) { result, subview in
            let size = subview.sizeThatFits(.unspecified)
            return CGSize(
                width: max(result.width, size.width),
                height: result.height + size.height)
        }
    }

    // This layout also needs a placeSubviews() implementation.
}
```

The implementation asks each subview for its ideal size by calling the [sizeThatFits(_:)](../LayoutSubview/sizeThatFits.zh-Hans.md) method with an [unspecified](../ProposedViewSize/unspecified.zh-Hans.md) proposed size. It then reduces these values into a single size that represents the maximum subview width and the sum of subview heights. Because this example isn’t flexible, it ignores its size proposal input and always returns the same value for a given set of subviews.

SwiftUI views choose their own size, so the layout engine always uses a value that you return from this method as the actual size of the composite view. That size factors into the construction of the `bounds` input to the [placeSubviews(in:proposal:subviews:cache:)](placeSubviews_in_proposal_subviews_cache.zh-Hans.md) method.

## Sizing the container and placing subviews

- **placeSubviews(in:proposal:subviews:cache:)**: Assigns positions to each of the layout’s subviews.
- **Layout.Subviews**: A collection of proxies for the subviews of a layout view.

