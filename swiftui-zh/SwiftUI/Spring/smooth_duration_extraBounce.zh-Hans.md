--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/smooth(duration:extraBounce:)

抓取时间：2025-12-01T11:04:00Z

---

# smooth(duration:extraBounce:)

**类型方法**

一个具有预定义持续时间且无回弹的平滑弹簧，其回弹速度可调。

## 声明

```swift
static func smooth(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Spring
```

## 参数

- **duration**：感知持续时间，定义弹簧的运行速度。该值近似等于弹簧的稳定持续时间，但对于回弹力非常强的弹簧，它将等于弹簧的振荡周期。

- **extraBounce**：在基础回弹力 0 的基础上增加多少回弹力。

## 获取内置弹簧

- **bouncy**：具有预设持续时间和较高回弹力的弹簧。

- **bouncy(duration:extraBounce:)**：具有预设持续时间和较高回弹力且可调节的弹簧。

- **smooth**：具有预设持续时间且无回弹力的平滑弹簧。

- **snappy**：具有预设持续时间和较小回弹力且感觉更灵敏的弹簧。

- **snappy(duration:extraBounce:)**：具有预设持续时间和较小回弹力且感觉更灵敏且可调节的弹簧。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/smooth(duration:extraBounce:)
crawled: 2025-12-01T11:04:00Z
---

# smooth(duration:extraBounce:)

**Type Method**

A smooth spring with a predefined duration and no bounce that can be tuned.

## Declaration

```swift
static func smooth(duration: TimeInterval = 0.5, extraBounce: Double = 0.0) -> Spring
```

## Parameters

- **duration**: The perceptual duration, which defines the pace of the spring. This is approximately equal to the settling duration, but for very bouncy springs, will be the duration of the period of oscillation for the spring.
- **extraBounce**: How much additional bounce should be added to the base bounce of 0.

## Getting built-in springs

- **bouncy**: A spring with a predefined duration and higher amount of bounce.
- **bouncy(duration:extraBounce:)**: A spring with a predefined duration and higher amount of bounce that can be tuned.
- **smooth**: A smooth spring with a predefined duration and no bounce.
- **snappy**: A spring with a predefined duration and small amount of bounce that feels more snappy.
- **snappy(duration:extraBounce:)**: A spring with a predefined duration and small amount of bounce that feels more snappy and can be tuned.

