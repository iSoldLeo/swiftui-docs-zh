--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/damping

抓取时间：2025-12-03T06:14:54Z

---

# 阻尼

**实例属性**

定义弹簧运动因摩擦力而产生的阻尼方式。

## 声明

```swift
var damping: Double { get }
```

## 说明

减小此值会减少每次振荡的能量损失：弹簧会越过其目标位置。增大此值会增加每次振荡的能量损失：振荡次数会减少，振幅也会减小。

## 获取弹簧特性

- **bounce**：弹簧的弹性。

- **dampingRatio**：施加的阻力大小，以产生临界阻尼所需阻力的百分比表示。

- **duration**：感知持续时间，用于定义弹簧的运动速度。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧的刚度，以秒为单位的近似持续时间来定义。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。

- **stiffness**：弹簧刚度系数。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/damping
crawled: 2025-12-03T06:14:54Z
---

# damping

**Instance Property**

Defines how the spring’s motion should be damped due to the forces of friction.

## Declaration

```swift
var damping: Double { get }
```

## Discussion

Reducing this value reduces the energy loss with each oscillation: the spring will overshoot its destination. Increasing the value increases the energy loss with each duration: there will be fewer and smaller oscillations.

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.
- **stiffness**: The spring stiffness coefficient.

