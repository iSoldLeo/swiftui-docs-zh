--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollTransition(_:axis:transition:)

抓取时间：2025-11-30T21:25:31Z

---

# scrollTransition(_:axis:transition:)

**实例方法**

应用指定的过渡效果，当此视图在其所在的滚动视图的可见区域内出现和消失时，会在过渡的各个阶段之间进行动画处理。

## 声明

```swift
nonisolated func scrollTransition(_ configuration: ScrollTransitionConfiguration = .interactive, axis: Axis? = nil, transition: @escaping (EmptyVisualEffect, ScrollTransitionPhase) -> some VisualEffect) -> some View

```

## 参数

- **configuration**：控制过渡效果应用方式的配置。此配置将在视图出现和消失时同时应用（过渡效果是对称的）。

- **axis**：应用过渡效果的滚动视图的轴。 `nil` 的默认值使用最内层包含滚动视图的轴，如果最内层滚动视图可沿两个轴滚动，则使用 `.vertical`。

- **transition**：一个闭包，用于根据提供的阶段应用视觉效果。

## 滚动过渡动画

- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**：应用给定的过渡效果，当此视图在包含滚动视图的可见区域内出现和消失时，在过渡的各个阶段之间进行动画切换。

- **ScrollTransitionPhase**：视图在其他视图之间滚动时所经历的过渡阶段。

- **ScrollTransitionConfiguration**：滚动过渡的配置，用于控制视图在包含滚动视图或其他容器的可见区域内滚动时如何应用过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollTransition(_:axis:transition:)
crawled: 2025-11-30T21:25:31Z
---

# scrollTransition(_:axis:transition:)

**Instance Method**

Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.

## Declaration

```swift
nonisolated func scrollTransition(_ configuration: ScrollTransitionConfiguration = .interactive, axis: Axis? = nil, transition: @escaping (EmptyVisualEffect, ScrollTransitionPhase) -> some VisualEffect) -> some View

```

## Parameters

- **configuration**: The configuration controlling how the transition will be applied. The configuration will be applied both while the view is coming into view and while it is disappearing (the transition is symmetrical).
- **axis**: The axis of the containing scroll view over which the transition will be applied. The default value of `nil` uses the axis of the innermost containing scroll view, or `.vertical` if the innermost scroll view is scrollable along both axes.
- **transition**: A closure that applies visual effects as a function of the provided phase.

## Animating scroll transitions

- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **ScrollTransitionPhase**: The phases that a view transitions between when it scrolls among other views.
- **ScrollTransitionConfiguration**: The configuration of a scroll transition that controls how a transition is applied as a view is scrolled through the visible region of a containing scroll view or other container.

