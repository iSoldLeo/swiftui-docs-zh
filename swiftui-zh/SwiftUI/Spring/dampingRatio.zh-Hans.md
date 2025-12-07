--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/dampingRatio
抓取时间：2025-12-03T06:14:55Z

---

# 阻尼比

**实例属性**

施加的阻力大小，以产生临界阻尼所需阻力的百分比表示。

## 声明

```swift
var dampingRatio: Double { get }
```

## 说明

当 `dampingRatio` 为 1 时，弹簧将平滑地减速到最终位置，不会振荡。阻尼比小于 1 时，弹簧会振荡得越来越厉害，直到完全停止。

## 获取弹簧特性

- **bounce**：弹簧的弹性。

- **damping**：定义弹簧运动因摩擦力而产生的阻尼方式。

- **duration**：感知持续时间，用于定义弹簧的运动速度。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧的刚度，以秒为单位的近似持续时间来定义。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。

- **stiffness**：弹簧刚度系数。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/dampingRatio
crawled: 2025-12-03T06:14:55Z
---

# dampingRatio

**Instance Property**

The amount of drag applied, as a fraction of the amount needed to produce critical damping.

## Declaration

```swift
var dampingRatio: Double { get }
```

## Discussion

When `dampingRatio` is 1, the spring will smoothly decelerate to its final position without oscillating. Damping ratios less than 1 will oscillate more and more before coming to a complete stop.

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.
- **stiffness**: The spring stiffness coefficient.

