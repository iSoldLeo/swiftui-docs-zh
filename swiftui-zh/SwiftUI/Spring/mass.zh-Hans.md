--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/mass
抓取时间：2025-12-03T06:14:56Z

---

# mass

**实例属性**

连接在弹簧末端的物体的质量。

## 声明

```swift
var mass: Double { get }
```

## 说明

默认质量值为 1。增加此值会增强弹簧的效果：连接的物体将经历更多次的振动和更大的过冲，从而延长稳定时间。减小质量值会减弱弹簧的效果：振动次数减少，过冲减小，从而缩短稳定时间。

## 获取弹簧特性

- **bounce**：弹簧的弹性。

- **damping**：定义弹簧运动因摩擦力而产生的阻尼方式。

- **dampingRatio**：施加的阻力大小，以产生临界阻尼所需阻力的百分比表示。

- **duration**：感知持续时间，定义弹簧的运动节奏。

- **response**：弹簧的刚度，以秒为单位的近似持续时间表示。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。

- **stiffness**：弹簧刚度系数。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/mass
crawled: 2025-12-03T06:14:56Z
---

# mass

**Instance Property**

The mass of the object attached to the end of the spring.

## Declaration

```swift
var mass: Double { get }
```

## Discussion

The default mass is 1. Increasing this value will increase the spring’s effect: the attached object will be subject to more oscillations and greater overshoot, resulting in an increased settling duration. Decreasing the mass will reduce the spring effect: there will be fewer oscillations and a reduced overshoot, resulting in a decreased settling duration.

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.
- **stiffness**: The spring stiffness coefficient.

