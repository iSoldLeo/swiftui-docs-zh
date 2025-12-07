---
来源： https://developer.apple.com/documentation/SwiftUI/Layout/Subviews
抓取时间： 2025-12-02T17:53:07Z
---

# Layout.Subviews

**类型别名**

布局视图子视图的代理集合。

## 声明

```swift
typealias Subviews = LayoutSubviews
```

## 讨论

这个集合不存储视图。它存储的是⟦DL_0003❾ 的实例，每个实例都是布局排列的视图的代理。使用代理可以获取有关视图的信息，并告诉视图在哪里出现。

有关底层集合类型行为的更多信息，请参阅[LayoutSubviews](../LayoutSubviews.zh-Hans.md)。

## 确定容器大小并放置子视图

- **sizeThatFits(proposal:subviews:cache:)**：根据建议的大小和视图的子视图，返回复合视图的大小。
- **placeSubviews(in:proposal:subviews:cache:)**：为布局的每个子视图指定位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout/Subviews
crawled: 2025-12-02T17:53:07Z
---

# Layout.Subviews

**Type Alias**

A collection of proxies for the subviews of a layout view.

## Declaration

```swift
typealias Subviews = LayoutSubviews
```

## Discussion

This collection doesn’t store views. Instead it stores instances of [LayoutSubview](../LayoutSubview.zh-Hans.md), each of which acts as a proxy for one of the views arranged by the layout. Use the proxies to get information about the views, and to tell the views where to appear.

For more information about the behavior of the underlying collection type, see [LayoutSubviews](../LayoutSubviews.zh-Hans.md).

## Sizing the container and placing subviews

- **sizeThatFits(proposal:subviews:cache:)**: Returns the size of the composite view, given a proposed size and the view’s subviews.
- **placeSubviews(in:proposal:subviews:cache:)**: Assigns positions to each of the layout’s subviews.

