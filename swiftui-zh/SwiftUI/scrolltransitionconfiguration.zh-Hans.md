--- 来源：https://developer.apple.com/documentation/swiftui/scrolltransitionconfiguration
抓取时间：2025-12-05T22:29:03Z

---

# ScrollTransitionConfiguration

**Structure**

滚动过渡的配置，用于控制当视图在其所在的滚动视图或其他容器的可见区域内滚动时，过渡效果的应用方式。

## 声明

```swift
struct ScrollTransitionConfiguration
```

## 获取配置

- **identity**：创建一个新的配置，该配置不会改变视图的外观。

- **animated**：创建一个新的配置，该配置会在视图变为可见时，以离散动画的方式添加过渡效果。

- **animated(_:)**：创建一个新的配置，该配置会在视图变为可见时，以离散动画的方式添加过渡效果。

- **interactive**：创建一个新的配置，当视图滚动到容器的可见区域时，以交互方式插值过渡效果。

- **interactive(timingCurve:)**：创建一个新的配置，当视图滚动到容器的可见区域时，以交互方式插值过渡效果。

## 访问配置

- **animation(_:)**：设置应用过渡效果的动画。

- **threshold(_:)**：设置视图完全可见的阈值。

- **ScrollTransitionConfiguration.Threshold**：描述目标视图在容器内从隐藏（完全位于容器外部）到可见的特定过程点。

## 滚动过渡动画

- **scrollTransition(_:axis:transition:)**：应用指定的过渡效果，当此视图在其包含的滚动视图的可见区域内出现和消失时，会在过渡的各个阶段之间进行动画切换。

- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**：应用指定的过渡效果，当此视图在其包含的滚动视图的可见区域内出现和消失时，会在过渡的各个阶段之间进行动画切换。

- **ScrollTransitionPhase**：视图在其他视图之间滚动时所经历的过渡阶段。


---
source: https://developer.apple.com/documentation/swiftui/scrolltransitionconfiguration
crawled: 2025-12-05T22:29:03Z
---

# ScrollTransitionConfiguration

**Structure**

The configuration of a scroll transition that controls how a transition is applied as a view is scrolled through the visible region of a containing scroll view or other container.

## Declaration

```swift
struct ScrollTransitionConfiguration
```

## Getting the configuration

- **identity**: Creates a new configuration that does not change the appearance of the view.
- **animated**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **animated(_:)**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **interactive**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.
- **interactive(timingCurve:)**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

## Accessing the configuration

- **animation(_:)**: Sets the animation with which the transition will be applied.
- **threshold(_:)**: Sets the threshold at which the view will be considered fully visible.
- **ScrollTransitionConfiguration.Threshold**: Describes a specific point in the progression of a target view within a container from hidden (fully outside the container) to visible.

## Animating scroll transitions

- **scrollTransition(_:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **ScrollTransitionPhase**: The phases that a view transitions between when it scrolls among other views.

