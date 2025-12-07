--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/force(target:position:velocity:)

抓取时间：2025-12-03T06:15:02Z

---

# force(target:position:velocity:)

**实例方法**

根据当前位置、目标位置和速度变化量计算弹簧所受的力。

## 声明

```swift
func force<V>(target: V, position: V, velocity: V) -> V where V : VectorArithmetic
```

## 说明

此值以每秒平方的向量类型为单位。

## 计算力和持续时间

- **force(fromValue:toValue:position:velocity:)**：根据当前位置、速度以及弹簧运动起始值和结束值的除数计算弹簧所受的力。

- **settlingDuration(target:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计持续时间。

- **settlingDuration(fromValue:toValue:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计持续时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/force(target:position:velocity:)
crawled: 2025-12-03T06:15:02Z
---

# force(target:position:velocity:)

**Instance Method**

Calculates the force upon the spring given a current position, target, and velocity amount of change.

## Declaration

```swift
func force<V>(target: V, position: V, velocity: V) -> V where V : VectorArithmetic
```

## Discussion

This value is in units of the vector type per second squared.

## Calculating forces and durations

- **force(fromValue:toValue:position:velocity:)**: Calculates the force upon the spring given a current position, velocity, and divisor from the starting and end values for the spring to travel.
- **settlingDuration(target:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.
- **settlingDuration(fromValue:toValue:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.

