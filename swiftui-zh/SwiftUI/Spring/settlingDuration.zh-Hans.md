--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/settlingDuration
抓取时间：2025-12-03T06:14:57Z

---

# settlingDuration

**实例属性**

弹簧系统达到静止状态所需的估计持续时间。

## 声明

```swift
var settlingDuration: TimeInterval { get }
```

## 说明

此处使用了 `target` 为 1.0、`initialVelocity` 为 0 和 `epsilon` 为 0.001。

## 获取弹簧特性

- **bounce**：弹簧的弹性。

- **damping**：定义弹簧运动因摩擦力而产生的阻尼方式。

- **dampingRatio**：施加的阻力大小，以产生临界阻尼所需阻力的百分比表示。

- **duration**：感知持续时间，定义弹簧的运动节奏。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧的刚度，以秒为单位的近似持续时间表示。

- **stiffness**：弹簧刚度系数。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/settlingDuration
crawled: 2025-12-03T06:14:57Z
---

# settlingDuration

**Instance Property**

The estimated duration required for the spring system to be considered at rest.

## Declaration

```swift
var settlingDuration: TimeInterval { get }
```

## Discussion

This uses a `target` of 1.0, an `initialVelocity` of 0, and an `epsilon` of 0.001.

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **stiffness**: The spring stiffness coefficient.

