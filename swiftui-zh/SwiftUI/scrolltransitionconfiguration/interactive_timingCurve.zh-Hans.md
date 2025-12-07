--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/interactive(timingCurve:)

抓取时间：2025-12-03T06:42:46Z

---

# interactive(timingCurve:)

**类型方法**

创建一个新的配置，当视图滚动到容器的可见区域时，该配置会交互式地插值过渡效果。

## 声明

```swift
static func interactive(timingCurve: UnitCurve = .easeInOut) -> ScrollTransitionConfiguration
```

## 参数

- **timingCurve**：用于调整过渡效果在各个阶段之间插值速度的曲线。例如，`.easeIn` 曲线会使插值在视图到达滚动视图边缘时缓慢开始，然后在到达可见阈值时加快。曲线在视图出现时“向前”应用，这意味着时间 0 对应于视图刚刚隐藏，时间 1.0 对应于视图达到配置阈值的点。这也意味着，当视图远离滚动视图中心时，时间曲线会反向应用。

## 返回值

一个基于当前滚动位置交互式插值过渡阶段的配置。

## 获取配置

- **identity**：创建一个不会改变视图外观的新配置。

- **animated**：创建一个在视图可见时以离散动画方式呈现过渡效果的新配置。

- **animated(_:)**：创建一个在视图可见时以离散动画方式呈现过渡效果的新配置。

- **interactive**：创建一个新的配置，当视图滚动到容器的可见区域时，该配置会以交互方式插值过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/interactive(timingCurve:)
crawled: 2025-12-03T06:42:46Z
---

# interactive(timingCurve:)

**Type Method**

Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

## Declaration

```swift
static func interactive(timingCurve: UnitCurve = .easeInOut) -> ScrollTransitionConfiguration
```

## Parameters

- **timingCurve**: The curve that adjusts the pace at which the effect is interpolated between phases of the transition. For example, an `.easeIn` curve causes interpolation to begin slowly as the view reaches the edge of the scroll view, then speed up as it reaches the visible threshold. The curve is applied ‘forward’ while the view is appearing, meaning that time zero corresponds to the view being just hidden, and time 1.0 corresponds to the pont at which the view reaches the configuration threshold. This also means that the timing curve is applied in reversed while the view is moving away from the center of the scroll view.

## Return Value

A configuration that interactively interpolates between transition phases based on the current scroll position.

## Getting the configuration

- **identity**: Creates a new configuration that does not change the appearance of the view.
- **animated**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **animated(_:)**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **interactive**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

