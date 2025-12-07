--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/interactive
抓取时间：2025-12-03T06:42:46Z

---

# interactive

**类型属性**

创建一个新的配置，当视图滚动到容器的可见区域时，该配置会以交互方式插值过渡效果。

## 声明

```swift
static let interactive: ScrollTransitionConfiguration
```

## 获取配置

- **identity**：创建一个新的配置，该配置不会改变视图的外观。

- **animated**：创建一个新的配置，该配置会在视图变为可见时以离散动画的方式添加过渡效果。

- **animated(_:)**：创建一个新的配置，该配置会在视图变为可见时以离散动画的方式添加过渡效果。

- **interactive(timingCurve:)**：创建一个新的配置，当视图滚动到容器的可见区域时，该配置会以交互方式插值过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/interactive
crawled: 2025-12-03T06:42:46Z
---

# interactive

**Type Property**

Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

## Declaration

```swift
static let interactive: ScrollTransitionConfiguration
```

## Getting the configuration

- **identity**: Creates a new configuration that does not change the appearance of the view.
- **animated**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **animated(_:)**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **interactive(timingCurve:)**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

