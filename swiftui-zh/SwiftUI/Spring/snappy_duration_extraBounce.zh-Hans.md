--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/snappy(duration:extraBounce:)

抓取时间：2025-12-03T06:14:53Z

---

# snappy(duration:extraBounce:)

**类型方法**

一个具有预定义持续时间和少量回弹力的弹簧，感觉更加灵敏，并且可以进行微调。

## 声明

```swift
static func snappy(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Spring
```

## 参数

- **duration**：感知持续时间，定义弹簧的节奏。它大致等于稳定持续时间，但对于回弹力非常强的弹簧，它将是弹簧振荡周期的持续时间。

- **extraBounce**：在基础回弹力 0.15 的基础上增加多少额外的回弹力。

## 获取内置弹簧

- **bouncy**：具有预设持续时间和较高回弹力的弹簧。

- **bouncy(duration:extraBounce:)**：具有预设持续时间和较高回弹力且可调节的弹簧。

- **smooth**：具有预设持续时间且无回弹力的平滑弹簧。

- **smooth(duration:extraBounce:)**：具有预设持续时间且无回弹力且可调节的平滑弹簧。

- **snappy**：具有预设持续时间和较小回弹力且感觉更灵敏的弹簧。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/snappy(duration:extraBounce:)
crawled: 2025-12-03T06:14:53Z
---

# snappy(duration:extraBounce:)

**Type Method**

A spring with a predefined duration and small amount of bounce that feels more snappy and can be tuned.

## Declaration

```swift
static func snappy(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Spring
```

## Parameters

- **duration**: The perceptual duration, which defines the pace of the spring. This is approximately equal to the settling duration, but for very bouncy springs, will be the duration of the period of oscillation for the spring.
- **extraBounce**: How much additional bounciness should be added to the base bounce of 0.15.

## Getting built-in springs

- **bouncy**: A spring with a predefined duration and higher amount of bounce.
- **bouncy(duration:extraBounce:)**: A spring with a predefined duration and higher amount of bounce that can be tuned.
- **smooth**: A smooth spring with a predefined duration and no bounce.
- **smooth(duration:extraBounce:)**: A smooth spring with a predefined duration and no bounce that can be tuned.
- **snappy**: A spring with a predefined duration and small amount of bounce that feels more snappy.

