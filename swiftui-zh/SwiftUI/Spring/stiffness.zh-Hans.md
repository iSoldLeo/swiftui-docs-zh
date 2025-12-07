--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/stiffness
抓取时间：2025-12-03T06:14:58Z

---

# 刚度

**实例属性**

弹簧刚度系数。

## 声明

```swift
var stiffness: Double { get }
```

## 说明

增加刚度会减少振荡次数，从而缩短稳定时间。降低刚度会增加振荡次数，从而延长稳定时间。

## 获取弹簧特性

- **bounce**：弹簧的弹性。

- **damping**：定义弹簧运动如何因摩擦力而衰减。

- **dampingRatio**：施加的阻力量，以产生临界阻尼所需阻力量的百分比表示。

- **duration**：感知持续时间，用于定义弹簧的运动速度。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧的刚度，以秒为单位的近似持续时间表示。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/stiffness
crawled: 2025-12-03T06:14:58Z
---

# stiffness

**Instance Property**

The spring stiffness coefficient.

## Declaration

```swift
var stiffness: Double { get }
```

## Discussion

Increasing the stiffness reduces the number of oscillations and will reduce the settling duration. Decreasing the stiffness increases the number of oscillations and will increase the settling duration.

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.

