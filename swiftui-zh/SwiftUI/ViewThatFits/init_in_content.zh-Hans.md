--- 来源：https://developer.apple.com/documentation/SwiftUI/ViewThatFits/init(in:content:)

抓取时间：2025-12-03T05:45:59Z

---

# init(in:content:)

**Initializer**

根据视图构建器提供的多个备选方案之一，生成一个在给定坐标轴上受限的视图。

## 声明

```swift
init(in axes: Axis.Set = [.horizontal, .vertical], @ViewBuilder content: () -> Content)
```

## 参数

- **axes**：用于约束子视图的坐标轴集合。该集合可以包含 [horizontal](../Axis/horizontal.zh-Hans.md)、[vertical](../Axis/vertical.zh-Hans.md) 或两者兼有。`ViewThatFits` 选择第一个尺寸符合这些坐标轴上指定尺寸的子视图。如果 `axes` 为空集，则 `ViewThatFits` 使用第一个子视图。默认情况下，`ViewThatFits` 使用两个轴。

- **content**：一个视图构建器，它按优先级顺序为此容器提供子视图。该构建器会选择第一个符合 `axes` 定义的建议宽度、高度或两者兼具的子视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewThatFits/init(in:content:)
crawled: 2025-12-03T05:45:59Z
---

# init(in:content:)

**Initializer**

Produces a view constrained in the given axes from one of several alternatives provided by a view builder.

## Declaration

```swift
init(in axes: Axis.Set = [.horizontal, .vertical], @ViewBuilder content: () -> Content)
```

## Parameters

- **axes**: A set of axes to constrain children to. The set may contain [horizontal](../Axis/horizontal.zh-Hans.md), [vertical](../Axis/vertical.zh-Hans.md), or both of these. `ViewThatFits` chooses the first child whose size fits within the proposed size on these axes. If `axes` is an empty set, `ViewThatFits` uses the first child view. By default, `ViewThatFits` uses both axes.
- **content**: A view builder that provides the child views for this container, in order of preference. The builder chooses the first child view that fits within the proposed width, height, or both, as defined by `axes`.

