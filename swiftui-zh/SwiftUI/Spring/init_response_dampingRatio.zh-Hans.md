--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/init(response:dampingRatio:)

抓取时间：2025-12-01T11:03:56Z

---

# init(response:dampingRatio:)

**Initializer**

创建一个具有指定响应和阻尼比的弹簧。

## 声明

```swift
init(response: Double, dampingRatio: Double)
```

## 参数

- **response**：定义弹簧的刚度，以秒为单位的近似持续时间。

- **dampingRatio**：定义施加的阻力，以产生临界阻尼所需阻力的百分比表示。

## 创建弹簧

- **init(duration:bounce:)**：创建一个具有指定持续时间和回弹力的弹簧。

- **init(mass:stiffness:damping:allowOverDamping:)**：创建具有指定质量、刚度和阻尼的弹簧。

- **init(settlingDuration:dampingRatio:epsilon:)**：创建具有指定持续时间和阻尼比的弹簧。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/init(response:dampingRatio:)
crawled: 2025-12-01T11:03:56Z
---

# init(response:dampingRatio:)

**Initializer**

Creates a spring with the specified response and damping ratio.

## Declaration

```swift
init(response: Double, dampingRatio: Double)
```

## Parameters

- **response**: Defines the stiffness of the spring as an approximate duration in seconds.
- **dampingRatio**: Defines the amount of drag applied as a fraction the amount needed to produce critical damping.

## Creating a spring

- **init(duration:bounce:)**: Creates a spring with the specified duration and bounce.
- **init(mass:stiffness:damping:allowOverDamping:)**: Creates a spring with the specified mass, stiffness, and damping.
- **init(settlingDuration:dampingRatio:epsilon:)**: Creates a spring with the specified duration and damping ratio.

