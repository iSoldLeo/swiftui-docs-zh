--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/init(duration:bounce:)

抓取时间：2025-12-01T11:03:55Z

---

# init(duration:bounce:)

**Initializer**

创建一个具有指定持续时间和弹跳值的弹簧。

## 声明

```swift
init(duration: TimeInterval = 0.5, bounce: Double = 0.0)
```

## 参数

- **duration**：定义弹簧的摆动速度。该值近似等于弹簧的稳定持续时间，但对于弹跳值非常大的弹簧，它将是弹簧振荡周期的持续时间。

- **bounce**：弹簧的弹跳力。值为 0 表示无弹跳（临界阻尼弹簧），正值表示弹跳量逐渐增加，最大值为 1.0（对应于无阻尼振荡），负值表示过阻尼弹簧，最小值为 -1.0。

## 创建弹簧

- **init(mass:stiffness:damping:allowOverDamping:)**：创建具有指定质量、刚度和阻尼的弹簧。

- **init(response:dampingRatio:)**：创建具有指定响应和阻尼比的弹簧。

- **init(settlingDuration:dampingRatio:epsilon:)**：创建具有指定持续时间和阻尼比的弹簧。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/init(duration:bounce:)
crawled: 2025-12-01T11:03:55Z
---

# init(duration:bounce:)

**Initializer**

Creates a spring with the specified duration and bounce.

## Declaration

```swift
init(duration: TimeInterval = 0.5, bounce: Double = 0.0)
```

## Parameters

- **duration**: Defines the pace of the spring. This is approximately equal to the settling duration, but for springs with very large bounce values, will be the duration of the period of oscillation for the spring.
- **bounce**: How bouncy the spring should be. A value of 0 indicates no bounces (a critically damped spring), positive values indicate increasing amounts of bounciness up to a maximum of 1.0 (corresponding to undamped oscillation), and negative values indicate overdamped springs with a minimum value of -1.0.

## Creating a spring

- **init(mass:stiffness:damping:allowOverDamping:)**: Creates a spring with the specified mass, stiffness, and damping.
- **init(response:dampingRatio:)**: Creates a spring with the specified response and damping ratio.
- **init(settlingDuration:dampingRatio:epsilon:)**: Creates a spring with the specified duration and damping ratio.

