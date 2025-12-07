---
来源：https://developer.apple.com/documentation/SwiftUI/Layout/spacing(subviews:cache:)
抓取时间： 2025-12-02T17:53:08Z
---

# spacing(subviews:cache:)

**实例方法**

返回复合视图的首选间距值。

## 声明

```swift
func spacing(subviews: Self.Subviews, cache: inout Self.Cache) -> ViewSpacing
```

## 参数

- **subviews**：代理实例集合，这些代理实例代表容器排列的视图。您可以使用该集合中的代理来获取有关子视图的信息，因为您可以确定容器更喜欢其周围的间距。
- **cache**：计算数据的可选存储空间，可在自定义布局容器的方法之间共享。详见 [makeCache(subviews:)](makeCache_subviews.zh-Hans.md)。

## 返回值

描述容器视图周围首选间距的 [ViewSpacing](../ViewSpacing.zh-Hans.md) 实例。

## 讨论

执行此方法可为布局容器提供自定义首选间距。您返回的值会影响容器周围的间距，但不会影响容器如何安排容器内相对于彼此的子视图。

使用默认值初始化一个容器，然后将其与某些子视图的间距实例合并，从而为容器创建一个自定义[ViewSpacing](../ViewSpacing.zh-Hans.md) 实例。例如，如果您定义了一个将子视图放置在一列中的基本垂直堆栈，您可以使用与容器边缘接触的子视图边缘的间距首选项：

```swift
extension BasicVStack {
    func spacing(subviews: Subviews, cache: inout ()) -> ViewSpacing {
        var spacing = ViewSpacing()

        for index in subviews.indices {
            var edges: Edge.Set = [.leading, .trailing]
            if index == 0 { edges.formUnion(.top) }
            if index == subviews.count - 1 { edges.formUnion(.bottom) }
            spacing.formUnion(subviews[index].spacing, edges: edges)
        }

        return spacing
    }
}
```

在上面的示例中，第一个和最后一个子视图分别影响容器上方和下方的间距，而所有子视图都会影响前缘和后缘的间距。

如果不执行此方法，协议提供的默认执行方式会合并所有边缘上所有子视图的间距首选项。

## 报告布局容器特征

- **explicitAlignment(of:in:proposal:subviews:cache:)**：返回指定的水平对齐向导沿 x 轴的位置。
- **layoutProperties**：布局容器的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/spacing(subviews:cache:)
crawled: 2025-12-02T17:53:08Z
---

# spacing(subviews:cache:)

**Instance Method**

Returns the preferred spacing values of the composite view.

## Declaration

```swift
func spacing(subviews: Self.Subviews, cache: inout Self.Cache) -> ViewSpacing
```

## Parameters

- **subviews**: A collection of proxy instances that represent the views that the container arranges. You can use the proxies in the collection to get information about the subviews as you determine how much spacing the container prefers around it.
- **cache**: Optional storage for calculated data that you can share among the methods of your custom layout container. See [makeCache(subviews:)](makeCache_subviews.zh-Hans.md) for details.

## Return Value

A [ViewSpacing](../ViewSpacing.zh-Hans.md) instance that describes the preferred spacing around the container view.

## Discussion

Implement this method to provide custom spacing preferences for a layout container. The value you return affects the spacing around the container, but it doesn’t affect how the container arranges subviews relative to one another inside the container.

Create a custom [ViewSpacing](../ViewSpacing.zh-Hans.md) instance for your container by initializing one with default values, and then merging that with spacing instances of certain subviews. For example, if you define a basic vertical stack that places subviews in a column, you could use the spacing preferences of the subview edges that make contact with the container’s edges:

```swift
extension BasicVStack {
    func spacing(subviews: Subviews, cache: inout ()) -> ViewSpacing {
        var spacing = ViewSpacing()

        for index in subviews.indices {
            var edges: Edge.Set = [.leading, .trailing]
            if index == 0 { edges.formUnion(.top) }
            if index == subviews.count - 1 { edges.formUnion(.bottom) }
            spacing.formUnion(subviews[index].spacing, edges: edges)
        }

        return spacing
    }
}
```

In the above example, the first and last subviews contribute to the spacing above and below the container, respectively, while all subviews affect the spacing on the leading and trailing edges.

If you don’t implement this method, the protocol provides a default implementation that merges the spacing preferences across all subviews on all edges.

## Reporting layout container characteristics

- **explicitAlignment(of:in:proposal:subviews:cache:)**: Returns the position of the specified horizontal alignment guide along the x axis.
- **layoutProperties**: Properties of a layout container.

