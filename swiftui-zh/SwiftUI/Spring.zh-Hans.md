--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring

抓取时间：2025-12-02T17:34:03Z

---

# Spring

**Structure**

弹簧运动的表示。

## 声明

```swift
struct Spring
```

## 概述

使用此类型可在不同的弹簧参数表示之间进行转换：

```swift
let spring = Spring(duration: 0.5, bounce: 0.3)
let (mass, stiffness, damping) = (spring.mass, spring.stiffness, spring.damping)
// (1.0, 157.9, 17.6)

let spring2 = Spring(mass: 1, stiffness: 100, damping: 10)
let (duration, bounce) = (spring2.duration, spring2.bounce)
// (0.63, 0.5)
```

您还可以使用它来查询给定输入集的弹簧位置和其他属性：

```swift
func unitPosition(time: TimeInterval) -> Double {
    let spring = Spring(duration: 0.5, bounce: 0.3)
    return spring.position(target: 1.0, time: time)
}
```

## 创建弹簧

- **init(duration:bounce:)**：创建具有指定持续时间和弹跳力的弹簧。

- **init(mass:stiffness:damping:allowOverDamping:)**：创建具有指定质量、刚度和阻尼的弹簧。

- **init(response:dampingRatio:)**：创建具有指定响应和阻尼比的弹簧。

- **init(settlingDuration:dampingRatio:epsilon:)**：创建具有指定持续时间和阻尼比的弹簧。

## 获取内置弹簧

- **bouncy**：具有预设持续时间和较大回弹量的弹簧。

- **bouncy(duration:extraBounce:)**：具有预设持续时间和较大回弹量的弹簧，且回弹量可调。

- **smooth**：具有预设持续时间且无回弹的平滑弹簧。

- **smooth(duration:extraBounce:)**：具有预设持续时间且无回弹的平滑弹簧，且回弹量可调。

- **snappy**：具有预设持续时间和较小回弹量的弹簧，回弹感更灵敏。

- **snappy(duration:extraBounce:)**：具有预设持续时间和少量回弹的弹簧，感觉更灵敏，并且可以调节。

## 获取弹簧特性

- **bounce**：弹簧的回弹力。

- **damping**：定义弹簧运动因摩擦力而产生的阻尼方式。

- **dampingRatio**：施加的阻力大小，以产生临界阻尼所需阻力的百分比表示。

- **duration**：感知持续时间，定义弹簧的弹跳速度。

- **mass**：连接在弹簧末端的物体的质量。

- **response**：弹簧的刚度，以秒为单位的近似持续时间表示。

- **settlingDuration**：弹簧系统达到静止状态所需的估计持续时间。

- **stiffness**：弹簧刚度系数。

## 获取弹簧状态

- **value(target:initialVelocity:time:)**：根据目标变化量，计算弹簧在给定时刻的值。

- **value(fromValue:toValue:initialVelocity:time:)**：根据弹簧行程的起始值和结束值，计算弹簧在给定时刻的值。

- **velocity(target:initialVelocity:time:)**：根据目标变化量，计算弹簧在给定时刻的速度。

- **velocity(fromValue:toValue:initialVelocity:time:)**：根据弹簧行程的起始值和结束值，计算弹簧在给定时刻的速度。

## 设置弹簧状态

- **update(value:velocity:target:deltaTime:)**：更新弹簧的当前值和速度。

## 计算力和持续时间

- **force(target:position:velocity:)**：根据当前位置、目标位置和速度变化量计算弹簧所受的力。

- **force(fromValue:toValue:position:velocity:)**：根据当前位置、速度以及弹簧运动起始值和结束值的除数计算弹簧所受的力。

- **settlingDuration(target:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计持续时间。

- **settlingDuration(fromValue:toValue:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计持续时间。

## 创建自定义动画

- **CustomAnimation**：定义可动画值随时间变化方式的类型。

- **AnimationContext**：自定义动画可用于管理状态和访问视图环境的上下文值。

- **AnimationState**：存储自定义动画状态的容器。

- **AnimationStateKey**：用于访问动画状态值的键。

- **UnitCurve**：由二维曲线定义的函数，该曲线将 [0,1] 范围内的输入进度映射到同样在 [0,1] 范围内的输出进度。通过改变曲线的形状，可以改变动画或其他插值的有效速度。

## 符合以下规范

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Spring
crawled: 2025-12-02T17:34:03Z
---

# Spring

**Structure**

A representation of a spring’s motion.

## Declaration

```swift
struct Spring
```

## Overview

Use this type to convert between different representations of spring parameters:

```swift
let spring = Spring(duration: 0.5, bounce: 0.3)
let (mass, stiffness, damping) = (spring.mass, spring.stiffness, spring.damping)
// (1.0, 157.9, 17.6)

let spring2 = Spring(mass: 1, stiffness: 100, damping: 10)
let (duration, bounce) = (spring2.duration, spring2.bounce)
// (0.63, 0.5)
```

You can also use it to query for a spring’s position and its other properties for a given set of inputs:

```swift
func unitPosition(time: TimeInterval) -> Double {
    let spring = Spring(duration: 0.5, bounce: 0.3)
    return spring.position(target: 1.0, time: time)
}
```

## Creating a spring

- **init(duration:bounce:)**: Creates a spring with the specified duration and bounce.
- **init(mass:stiffness:damping:allowOverDamping:)**: Creates a spring with the specified mass, stiffness, and damping.
- **init(response:dampingRatio:)**: Creates a spring with the specified response and damping ratio.
- **init(settlingDuration:dampingRatio:epsilon:)**: Creates a spring with the specified duration and damping ratio.

## Getting built-in springs

- **bouncy**: A spring with a predefined duration and higher amount of bounce.
- **bouncy(duration:extraBounce:)**: A spring with a predefined duration and higher amount of bounce that can be tuned.
- **smooth**: A smooth spring with a predefined duration and no bounce.
- **smooth(duration:extraBounce:)**: A smooth spring with a predefined duration and no bounce that can be tuned.
- **snappy**: A spring with a predefined duration and small amount of bounce that feels more snappy.
- **snappy(duration:extraBounce:)**: A spring with a predefined duration and small amount of bounce that feels more snappy and can be tuned.

## Getting spring characteristics

- **bounce**: How bouncy the spring is.
- **damping**: Defines how the spring’s motion should be damped due to the forces of friction.
- **dampingRatio**: The amount of drag applied, as a fraction of the amount needed to produce critical damping.
- **duration**: The perceptual duration, which defines the pace of the spring.
- **mass**: The mass of the object attached to the end of the spring.
- **response**: The stiffness of the spring, defined as an approximate duration in seconds.
- **settlingDuration**: The estimated duration required for the spring system to be considered at rest.
- **stiffness**: The spring stiffness coefficient.

## Getting spring state

- **value(target:initialVelocity:time:)**: Calculates the value of the spring at a given time given a target amount of change.
- **value(fromValue:toValue:initialVelocity:time:)**: Calculates the value of the spring at a given time for a starting and ending value for the spring to travel.
- **velocity(target:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a target amount of change.
- **velocity(fromValue:toValue:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a starting and ending value for the spring to travel.

## Setting spring state

- **update(value:velocity:target:deltaTime:)**: Updates the current  value and velocity of a spring.

## Calculating forces and durations

- **force(target:position:velocity:)**: Calculates the force upon the spring given a current position, target, and velocity amount of change.
- **force(fromValue:toValue:position:velocity:)**: Calculates the force upon the spring given a current position, velocity, and divisor from the starting and end values for the spring to travel.
- **settlingDuration(target:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.
- **settlingDuration(fromValue:toValue:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.

## Creating custom animations

- **CustomAnimation**: A type that defines how an animatable value changes over time.
- **AnimationContext**: Contextual values that a custom animation can use to manage state and access a view’s environment.
- **AnimationState**: A container that stores the state for a custom animation.
- **AnimationStateKey**: A key for accessing animation state values.
- **UnitCurve**: A  function defined by a two-dimensional curve that maps an input progress in the range [0,1] to an output progress that is also in the range [0,1]. By changing the shape of the curve, the effective speed of an animation or other interpolation can be changed.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

