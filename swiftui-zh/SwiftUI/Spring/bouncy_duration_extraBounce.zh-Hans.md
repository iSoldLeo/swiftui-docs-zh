--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/bouncy(duration:extraBounce:)

抓取时间：2025-12-03T06:14:49Z

---

# bouncy(duration:extraBounce:)

**类型方法**

一个具有预定义持续时间和可调节的更高弹跳力的弹簧。

## 声明

```swift
static func bouncy(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Spring
```

## 参数

- **duration**：感知持续时间，定义弹簧的弹跳速度。它大致等于稳定持续时间，但对于弹跳力非常强的弹簧，它将是弹簧振荡周期的持续时间。

- **extraBounce**：在基础弹跳力 0.3 的基础上增加的额外弹跳力。

## 获取内置弹簧

- **bouncy**：具有预设持续时间和较高回弹力的弹簧。

- **smooth**：具有预设持续时间且无回弹力的平滑弹簧。

- **smooth(duration:extraBounce:)**：具有预设持续时间且无回弹力的平滑弹簧，但可调节。

- **snappy**：具有预设持续时间和较小回弹力的弹簧，感觉更灵敏。

- **snappy(duration:extraBounce:)**：具有预设持续时间和较小回弹力的弹簧，感觉更灵敏且可调节。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/bouncy(duration:extraBounce:)
crawled: 2025-12-03T06:14:49Z
---

# bouncy(duration:extraBounce:)

**Type Method**

A spring with a predefined duration and higher amount of bounce that can be tuned.

## Declaration

```swift
static func bouncy(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Spring
```

## Parameters

- **duration**: The perceptual duration, which defines the pace of the spring. This is approximately equal to the settling duration, but for very bouncy springs, will be the duration of the period of oscillation for the spring.
- **extraBounce**: How much additional bounce should be added to the base bounce of 0.3.

## Getting built-in springs

- **bouncy**: A spring with a predefined duration and higher amount of bounce.
- **smooth**: A smooth spring with a predefined duration and no bounce.
- **smooth(duration:extraBounce:)**: A smooth spring with a predefined duration and no bounce that can be tuned.
- **snappy**: A spring with a predefined duration and small amount of bounce that feels more snappy.
- **snappy(duration:extraBounce:)**: A spring with a predefined duration and small amount of bounce that feels more snappy and can be tuned.

