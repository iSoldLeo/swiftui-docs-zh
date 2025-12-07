--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/init(settlingDuration:dampingRatio:epsilon:)

抓取时间：2025-12-03T06:14:48Z
---

# init(settlingDuration:dampingRatio:epsilon:)

**Initializer**

创建一个具有指定持续时间和阻尼比的弹簧。

## 声明

```swift
init(settlingDuration: TimeInterval, dampingRatio: Double, epsilon: Double = 0.001)
```

## 参数

- **settlingDuration**：弹簧停止运动所需的大约时间。

- **dampingRatio**：施加的阻力值，以达到临界阻尼所需的阻力值的百分比表示。

- **epsilon**：弹簧达到稳定状态前，所有后续值必须小于此阈值。

## 创建弹簧

- **init(duration:bounce:)**：创建具有指定持续时间和回弹力的弹簧。

- **init(mass:stiffness:damping:allowOverDamping:)**：创建具有指定质量、刚度和阻尼的弹簧。

- **init(response:dampingRatio:)**：创建具有指定响应和阻尼比的弹簧。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/init(settlingDuration:dampingRatio:epsilon:)
crawled: 2025-12-03T06:14:48Z
---

# init(settlingDuration:dampingRatio:epsilon:)

**Initializer**

Creates a spring with the specified duration and damping ratio.

## Declaration

```swift
init(settlingDuration: TimeInterval, dampingRatio: Double, epsilon: Double = 0.001)
```

## Parameters

- **settlingDuration**: The approximate time it will take for the spring to come to rest.
- **dampingRatio**: The amount of drag applied as a fraction of the amount needed to produce critical damping.
- **epsilon**: The threshhold for how small all subsequent values need to be before the spring is considered to have settled.

## Creating a spring

- **init(duration:bounce:)**: Creates a spring with the specified duration and bounce.
- **init(mass:stiffness:damping:allowOverDamping:)**: Creates a spring with the specified mass, stiffness, and damping.
- **init(response:dampingRatio:)**: Creates a spring with the specified response and damping ratio.

