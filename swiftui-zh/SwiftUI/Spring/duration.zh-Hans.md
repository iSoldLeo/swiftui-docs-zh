--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/duration
抓取时间：2025-12-03T06:14:55Z

---

# duration

**实例属性**

感知持续时间，定义弹簧的运动速度。

## 声明

```swift
var duration: TimeInterval { get }
```

## 获取弹簧特性

- **bounce**：弹簧的弹性。

- **damping**：定义弹簧运动因摩擦力而产生的阻尼。

- **dampingRatio**：施加的阻力大小，以产生临界阻尼所需阻力的百分比表示。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧刚度，定义为以秒为单位的近似持续时间。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。

- **stiffness**：弹簧刚度系数。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/duration
crawled: 2025-12-03T06:14:55Z
---

# duration

**Instance Property**

The perceptual duration, which defines the pace of the spring.

## Declaration

```swift
var duration: TimeInterval { get }
```

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.
- **stiffness**: The spring stiffness coefficient.

