--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollTransition(topLeading:bottomTrailing:axis:transition:)

抓取时间：2025-12-02T17:40:27Z

---

# scrollTransition(topLeading:bottomTrailing:axis:transition:)

**实例方法**

应用指定的过渡效果，当此视图在包含它的滚动视图的可见区域内出现和消失时，会在过渡的各个阶段之间进行动画处理。

## 声明

```swift
nonisolated func scrollTransition(topLeading: ScrollTransitionConfiguration, bottomTrailing: ScrollTransitionConfiguration, axis: Axis? = nil, transition: @escaping (EmptyVisualEffect, ScrollTransitionPhase) -> some VisualEffect) -> some View

```

## 参数

- **topLeading**：用于驱动视图即将出现在垂直滚动视图的顶部边缘或水平滚动视图的前缘时的过渡效果的配置。

- **bottomTrailing**：用于驱动视图即将出现在垂直滚动视图底部边缘或水平滚动视图尾部边缘时的过渡效果的配置。

- **axis**：应用过渡效果的包含滚动视图的轴线。默认值 `nil` 使用最内层包含滚动视图的轴线，如果最内层滚动视图可沿两个轴线滚动，则使用 `.vertical`。

- **transition**：要应用的过渡效果。

## 滚动过渡动画

- **scrollTransition(_:axis:transition:)**：应用指定的过渡效果，并在视图出现在包含滚动视图的可见区域内以及消失时，在过渡的各个阶段之间进行动画处理。

- **ScrollTransitionPhase**：视图在其他视图之间滚动时所经历的过渡阶段。

- **ScrollTransitionConfiguration**：滚动过渡的配置，用于控制视图在包含滚动视图或其他容器的可见区域内滚动时如何应用过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollTransition(topLeading:bottomTrailing:axis:transition:)
crawled: 2025-12-02T17:40:27Z
---

# scrollTransition(topLeading:bottomTrailing:axis:transition:)

**Instance Method**

Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.

## Declaration

```swift
nonisolated func scrollTransition(topLeading: ScrollTransitionConfiguration, bottomTrailing: ScrollTransitionConfiguration, axis: Axis? = nil, transition: @escaping (EmptyVisualEffect, ScrollTransitionPhase) -> some VisualEffect) -> some View

```

## Parameters

- **topLeading**: The configuration that drives the transition when the view is about to appear at the top edge of a vertical scroll view, or the leading edge of a horizont scroll view.
- **bottomTrailing**: The configuration that drives the transition when the view is about to appear at the bottom edge of a vertical scroll view, or the trailing edge of a horizont scroll view.
- **axis**: The axis of the containing scroll view over which the transition will be applied. The default value of `nil` uses the axis of the innermost containing scroll view, or `.vertical` if the innermost scroll view is scrollable along both axes.
- **transition**: The transition to apply.

## Animating scroll transitions

- **scrollTransition(_:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **ScrollTransitionPhase**: The phases that a view transitions between when it scrolls among other views.
- **ScrollTransitionConfiguration**: The configuration of a scroll transition that controls how a transition is applied as a view is scrolled through the visible region of a containing scroll view or other container.

