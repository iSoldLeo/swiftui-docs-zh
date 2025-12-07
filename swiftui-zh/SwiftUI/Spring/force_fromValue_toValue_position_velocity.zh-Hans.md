--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/force(fromValue:toValue:position:velocity:)

抓取时间：2025-12-03T06:15:03Z

---

# force(fromValue:toValue:position:velocity:)

**实例方法**

根据弹簧的当前位置、速度以及起始位置和结束位置的除数，计算弹簧所受的力。

## 声明

```swift
func force<V>(fromValue: V, toValue: V, position: V, velocity: V) -> V where V : Animatable
```

## 说明

此值的单位为每秒平方的向量类型。

## 计算力和持续时间

- **force(target:position:velocity:)**：根据弹簧的当前位置、目标位置和速度变化量，计算弹簧所受的力。

- **settlingDuration(target:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计持续时间。

- **settlingDuration(fromValue:toValue:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/force(fromValue:toValue:position:velocity:)
crawled: 2025-12-03T06:15:03Z
---

# force(fromValue:toValue:position:velocity:)

**Instance Method**

Calculates the force upon the spring given a current position, velocity, and divisor from the starting and end values for the spring to travel.

## Declaration

```swift
func force<V>(fromValue: V, toValue: V, position: V, velocity: V) -> V where V : Animatable
```

## Discussion

This value is in units of the vector type per second squared.

## Calculating forces and durations

- **force(target:position:velocity:)**: Calculates the force upon the spring given a current position, target, and velocity amount of change.
- **settlingDuration(target:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.
- **settlingDuration(fromValue:toValue:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.

