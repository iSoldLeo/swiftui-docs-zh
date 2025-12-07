---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubviews
抓取时间： 2025-12-02T16:16:01Z
---

# 布局子视图

**Structure**

表示布局视图子视图的代理值集合。

### 声明

```swift
struct LayoutSubviews
```

## 概览

您在实现[Layout](Layout.zh-Hans.md) 协议方法（如 [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 和 [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) ）时，会收到`LayoutSubviews` 输入。`subviews`参数（协议将其别名为[Subviews](Layout/Subviews.zh-Hans.md)类型）是一个包含布局子视图（[LayoutSubview](LayoutSubview.zh-Hans.md)类型）代理的集合。代理在集合中出现的顺序与它们在布局容器的[ViewBuilder](ViewBuilder.zh-Hans.md) 输入中出现的顺序相同。使用代理执行布局操作。

访问集合中的代理时，就像访问任何 Swift 随机访问集合的内容一样。例如，您可以枚举所有子视图及其索引，以检查或操作它们：

```swift
for (index, subview) in subviews.enumerated() {
    // ...
}
```

## 获取布局方向

- **layoutDirection**：容器视图继承的布局方向。

## 访问子视图

- **subscript(_:)**：获取指定范围内的子视图代理。
- **startIndex**：第一个子视图的索引。
- **endIndex**：第一个子视图的索引：比最后一个子视图高一级的索引。
- **LayoutSubviews.Element**：包含代理值的类型。
- **LayoutSubviews.Index**：包含代理值的类型：可用于索引代理值的类型。
- **LayoutSubviews.SubSequence**：包含代理值子序列的类型。

## 创建自定义布局容器

- 使用 SwiftUI 构建自定义布局**：使用 SwiftUI 提供的布局工具在应用程序界面中排列视图。
- **Layout**：定义视图集合几何图形的类型。
- **LayoutSubview**：表示布局中一个子视图的代理。

## 符合

- 双向集合
- 集合
- 等价
- 随机访问集合
- 可发送
- 可发送元类型
- 序列


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubviews
crawled: 2025-12-02T16:16:01Z
---

# LayoutSubviews

**Structure**

A collection of proxy values that represent the subviews of a layout view.

## Declaration

```swift
struct LayoutSubviews
```

## Overview

You receive a `LayoutSubviews` input to your implementations of [Layout](Layout.zh-Hans.md) protocol methods, like [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) and [sizeThatFits(proposal:subviews:cache:)](Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md). The `subviews` parameter (which the protocol aliases to the [Subviews](Layout/Subviews.zh-Hans.md) type) is a collection that contains proxies for the layout’s subviews (of type [LayoutSubview](LayoutSubview.zh-Hans.md)). The proxies appear in the collection in the same order that they appear in the [ViewBuilder](ViewBuilder.zh-Hans.md) input to the layout container. Use the proxies to perform layout operations.

Access the proxies in the collection as you would the contents of any Swift random-access collection. For example, you can enumerate all of the subviews and their indices to inspect or operate on them:

```swift
for (index, subview) in subviews.enumerated() {
    // ...
}
```

## Getting the layout direction

- **layoutDirection**: The layout direction inherited by the container view.

## Accessing subviews

- **subscript(_:)**: Gets the subview proxies in the specified range.
- **startIndex**: The index of the first subview.
- **endIndex**: An index that’s one higher than the last subview.
- **LayoutSubviews.Element**: A type that contains a proxy value.
- **LayoutSubviews.Index**: A type that you can use to index proxy values.
- **LayoutSubviews.SubSequence**: A type that contains a subsequence of proxy values.

## Creating a custom layout container

- **Composing custom layouts with SwiftUI**: Arrange views in your app’s interface using layout tools that SwiftUI provides.
- **Layout**: A type that defines the geometry of a collection of views.
- **LayoutSubview**: A proxy that represents one subview of a layout.

## Conforms To

- BidirectionalCollection
- Collection
- Equatable
- RandomAccessCollection
- Sendable
- SendableMetatype
- Sequence

