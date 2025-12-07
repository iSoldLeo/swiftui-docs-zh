--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/animated(_:)

抓取时间：2025-12-03T06:42:45Z

---

# animated(_:)

**类型方法**

创建一个新的配置，用于在视图变为可见时以离散动画的方式进行过渡。

## 声明

```swift
static func animated(_ animation: Animation = .default) -> ScrollTransitionConfiguration
```

## 参数

- **animation**：用于在状态之间过渡的动画。

## 返回值

一个在过渡阶段之间以离散动画方式进行的配置。

## 说明

与交互式配置不同，此配置的过渡动画不会在滚动视图滚动时进行插值。相反，过渡阶段仅在达到阈值后才会改变，此时将使用指定的动画来过渡到新的阶段。

## 获取配置

- **identity**：创建一个新配置，该配置不会改变视图的外观。

- **animated**：创建一个新配置，该配置会在视图变为可见时以离散动画的方式添加过渡效果。

- **interactive**：创建一个新配置，该配置会在视图滚动到容器的可见区域时，以交互方式插值过渡效果。

- **interactive(timingCurve:)**：创建一个新配置，该配置会在视图滚动到容器的可见区域时，以交互方式插值过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/animated(_:)
crawled: 2025-12-03T06:42:45Z
---

# animated(_:)

**Type Method**

Creates a new configuration that discretely animates the transition when the view becomes visible.

## Declaration

```swift
static func animated(_ animation: Animation = .default) -> ScrollTransitionConfiguration
```

## Parameters

- **animation**: The animation to use when transitioning between states.

## Return Value

A configuration that discretely animates between transition phases.

## Discussion

Unlike the interactive configuration, the transition isn’t interpolated as the scroll view is scrolled. Instead, the transition phase only changes once the threshold has been reached, at which time the given animation is used to animate to the new phase.

## Getting the configuration

- **identity**: Creates a new configuration that does not change the appearance of the view.
- **animated**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **interactive**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.
- **interactive(timingCurve:)**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

