---
来源：https://developer.apple.com/documentation/SwiftUI/Layout/explicitAlignment(of:in:proposal:subviews:cache:)
抓取时间： 2025-11-30T21:37:51Z
---

# explicitAlignment(of:in:proposal:subviews:cache:)

**实例方法**

返回指定水平对齐向导沿 x 轴的位置。

## 声明

```swift
func explicitAlignment(of guide: HorizontalAlignment, in bounds: CGRect, proposal: ProposedViewSize, subviews: Self.Subviews, cache: inout Self.Cache) -> CGFloat?
```

## 参数

- **guide**：方法计算位置的 [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) 导向。
- **bounds**：容器视图的父视图分配给容器视图的区域，在父视图的坐标空间中指定。
- **proposal**：容器的建议尺寸。
- **subviews**：代理实例集合，代表容器安排的视图。您可以使用该集合中的代理来获取有关子视图的信息，从而确定放置向导的位置。
- **cache**：计算数据的可选存储空间，可在自定义布局容器的方法之间共享。详见 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md)。

## 返回值

向导相对于 `bounds` 的位置。返回`nil` 表示向导没有明确的值。

## 讨论

执行此方法可返回自定义布局容器的指定对齐方式的值。返回的值会影响容器的整体布局，但不会影响容器如何相对排列子视图。

您可以使用此方法将对齐方式设置在非标准位置。例如，可以将容器的前缘对齐向导缩进 10 点：

```swift
extension BasicVStack {
    func explicitAlignment(
        of guide: HorizontalAlignment,
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) -> CGFloat? {
        if guide == .leading {
            return bounds.minX + 10
        }
        return nil
    }
}
```

上例中，其他向导返回`nil`，表示它们没有明确的值。没有显式值的向导的行为与其他视图相同。如果您没有实现该方法，协议的默认实现将合并子视图的引导符。

## 报告布局容器特征

- **spacing(subviews:cache:)**：返回复合视图的首选间距值。
- **layoutProperties**：布局容器的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/explicitAlignment(of:in:proposal:subviews:cache:)
crawled: 2025-11-30T21:37:51Z
---

# explicitAlignment(of:in:proposal:subviews:cache:)

**Instance Method**

Returns the position of the specified horizontal alignment guide along the x axis.

## Declaration

```swift
func explicitAlignment(of guide: HorizontalAlignment, in bounds: CGRect, proposal: ProposedViewSize, subviews: Self.Subviews, cache: inout Self.Cache) -> CGFloat?
```

## Parameters

- **guide**: The [HorizontalAlignment](../HorizontalAlignment.zh-Hans.md) guide that the method calculates the position of.
- **bounds**: The region that the container view’s parent allocates to the container view, specified in the parent’s coordinate space.
- **proposal**: A proposed size for the container.
- **subviews**: A collection of proxy instances that represent the views arranged by the container. You can use the proxies in the collection to get information about the subviews as you determine where to place the guide.
- **cache**: Optional storage for calculated data that you can share among the methods of your custom layout container. See [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) for details.

## Return Value

The guide’s position relative to the `bounds`. Return `nil` to indicate that the guide doesn’t have an explicit value.

## Discussion

Implement this method to return a value for the specified alignment guide of a custom layout container. The value you return affects the placement of the container as a whole, but it doesn’t affect how the container arranges subviews relative to one another.

You can use this method to put an alignment guide in a nonstandard position. For example, you can indent the container’s leading edge alignment guide by 10 points:

```swift
extension BasicVStack {
    func explicitAlignment(
        of guide: HorizontalAlignment,
        in bounds: CGRect,
        proposal: ProposedViewSize,
        subviews: Subviews,
        cache: inout ()
    ) -> CGFloat? {
        if guide == .leading {
            return bounds.minX + 10
        }
        return nil
    }
}
```

The above example returns `nil` for other guides to indicate that they don’t have an explicit value. A guide without an explicit value behaves as it would for any other view. If you don’t implement the method, the protocol’s default implementation merges the subviews’ guides.

## Reporting layout container characteristics

- **spacing(subviews:cache:)**: Returns the preferred spacing values of the composite view.
- **layoutProperties**: Properties of a layout container.

