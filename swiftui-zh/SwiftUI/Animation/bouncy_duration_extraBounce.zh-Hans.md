---
来源：https://developer.apple.com/documentation/SwiftUI/Animation/bouncy(持续时间：extraBounce:)
抓取时间：2025-12-03T06:12:11Z
---

# bouncy(duration:extraBounce:)

**类型方法**

一种弹簧动画，具有预定义的持续时间和可调整的较高弹跳量。

## 声明

```swift
static func bouncy(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Animation
```

## 参数

- **duration**：感知持续时间，定义弹簧的节奏。它大致等同于稳定持续时间，但对于弹力很强的弹簧，它将是弹簧振荡周期的持续时间。
- **extraBounce**：在 0.3 的基础弹力上应增加多少额外弹力。

## 获取内置弹簧动画

- **bouncy**：具有预定义持续时间和更高弹跳量的弹簧动画。
- **smooth**：平滑的弹簧动画，具有预定义的持续时间且无弹跳。
- **smooth(duration:extraBounce:)**：可调整的平滑弹簧动画，具有预定义的持续时间，无反弹。
- **snappy**：具有预定义持续时间和少量反弹的弹簧动画，感觉更敏捷。
- **snappy(duration:extraBounce:)**：具有预定义持续时间和少量弹跳的弹簧动画，感觉更敏捷，并可进行调整。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/bouncy(duration:extraBounce:)
crawled: 2025-12-03T06:12:11Z
---

# bouncy(duration:extraBounce:)

**Type Method**

A spring animation with a predefined duration and higher amount of bounce that can be tuned.

## Declaration

```swift
static func bouncy(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Animation
```

## Parameters

- **duration**: The perceptual duration, which defines the pace of the spring. This is approximately equal to the settling duration, but for very bouncy springs, will be the duration of the period of oscillation for the spring.
- **extraBounce**: How much additional bounce should be added to the base bounce of 0.3.

## Getting built-in spring animations

- **bouncy**: A spring animation with a predefined duration and higher amount of bounce.
- **smooth**: A smooth spring animation with a predefined duration and no bounce.
- **smooth(duration:extraBounce:)**: A smooth spring animation with a predefined duration and no bounce that can be tuned.
- **snappy**: A spring animation with a predefined duration and small amount of bounce that feels more snappy.
- **snappy(duration:extraBounce:)**: A spring animation with a predefined duration and small amount of bounce that feels more snappy and can be tuned.

