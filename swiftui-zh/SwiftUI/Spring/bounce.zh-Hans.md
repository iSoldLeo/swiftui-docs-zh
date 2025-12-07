--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/bounce
抓取时间：2025-12-03T06:14:53Z

---

# bounce

**实例属性**

弹簧的弹性。

## 声明

```swift
var bounce: Double { get }
```

## 说明

值为 0 表示无弹性（临界阻尼弹簧），正值表示弹性逐渐增加，最大值为 1.0（对应于无阻尼振荡），负值表示过阻尼弹簧，最小值为 -1.0。

## 获取弹簧特性

- **damping**：定义弹簧运动如何因摩擦力而衰减。

- **dampingRatio**：施加的阻力量，以产生临界阻尼所需阻力量的百分比表示。

- **duration**：感知持续时间，用于定义弹簧的运动速度。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧的刚度，以秒为单位的近似持续时间表示。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。

- **stiffness**：弹簧刚度系数。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/bounce
crawled: 2025-12-03T06:14:53Z
---

# bounce

**Instance Property**

How bouncy the spring is.

## Declaration

```swift
var bounce: Double { get }
```

## Discussion

A value of 0 indicates no bounces (a critically damped spring), positive values indicate increasing amounts of bounciness up to a maximum of 1.0 (corresponding to undamped oscillation), and negative values indicate overdamped springs with a minimum value of -1.0.

## Getting spring characteristics

- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.
- **stiffness**: The spring stiffness coefficient.

