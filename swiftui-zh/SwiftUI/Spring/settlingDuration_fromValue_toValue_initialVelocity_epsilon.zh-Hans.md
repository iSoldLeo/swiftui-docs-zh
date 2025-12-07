--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/settlingDuration(fromValue:toValue:initialVelocity:epsilon:)

抓取时间：2025-12-01T11:04:13Z

---

# settlingDuration(fromValue:toValue:initialVelocity:epsilon:)

**实例方法**

弹簧系统达到静止状态所需的估计持续时间。

## 声明

```swift
func settlingDuration<V>(fromValue: V, toValue: V, initialVelocity: V, epsilon: Double) -> TimeInterval where V : Animatable
```

## 说明

epsilon 值指定了弹簧达到静止状态之前，所有后续值需要小于多少才能被视为弹簧已稳定。

## 计算力和持续时间

- **force(target:position:velocity:)**：根据当前位置、目标位置和速度变化量计算弹簧所受的力。

- **force(fromValue:toValue:position:velocity:)**：根据弹簧的当前位置、速度以及起始位置和终止位置的除数，计算弹簧所受的力。

- **settlingDuration(target:initialVelocity:epsilon:)**：弹簧系统达到静止状态所需的估计时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/settlingDuration(fromValue:toValue:initialVelocity:epsilon:)
crawled: 2025-12-01T11:04:13Z
---

# settlingDuration(fromValue:toValue:initialVelocity:epsilon:)

**Instance Method**

The estimated duration required for the spring system to be considered at rest.

## Declaration

```swift
func settlingDuration<V>(fromValue: V, toValue: V, initialVelocity: V, epsilon: Double) -> TimeInterval where V : Animatable
```

## Discussion

The epsilon value specifies the threshold for how small all subsequent values need to be before the spring is considered to have settled.

## Calculating forces and durations

- **force(target:position:velocity:)**: Calculates the force upon the spring given a current position, target, and velocity amount of change.
- **force(fromValue:toValue:position:velocity:)**: Calculates the force upon the spring given a current position, velocity, and divisor from the starting and end values for the spring to travel.
- **settlingDuration(target:initialVelocity:epsilon:)**: The estimated duration required for the spring system to be considered at rest.

