--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/identity
抓取时间：2025-12-03T06:42:43Z

---

# identity

**类型属性**

创建一个新的配置，该配置不会改变视图的外观。

## 声明

```swift
static let identity: ScrollTransitionConfiguration
```

## 获取配置

- **animated**：创建一个新的配置，当视图变为可见时，以离散动画的方式添加过渡效果。

- **animated(_:)**：创建一个新的配置，当视图变为可见时，以离散动画的方式添加过渡效果。

- **interactive**：创建一个新的配置，当视图滚动到容器的可见区域时，以交互方式插值过渡效果。

- **interactive(timingCurve:)**：创建一个新的配置，当视图滚动到容器的可见区域时，该配置会以交互方式插值过渡效果。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/identity
crawled: 2025-12-03T06:42:43Z
---

# identity

**Type Property**

Creates a new configuration that does not change the appearance of the view.

## Declaration

```swift
static let identity: ScrollTransitionConfiguration
```

## Getting the configuration

- **animated**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **animated(_:)**: Creates a new configuration that discretely animates the transition when the view becomes visible.
- **interactive**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.
- **interactive(timingCurve:)**: Creates a new configuration that interactively interpolates the transition’s effect as the view is scrolled into the visible region of the container.

