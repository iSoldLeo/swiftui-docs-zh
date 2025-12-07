--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/value(target:initialVelocity:time:)

抓取时间：2025-12-01T11:04:07Z

---

# value(target:initialVelocity:time:)

**实例方法**

根据目标变化量，计算弹簧在给定时间点的值。

## 声明

```swift
func value<V>(target: V, initialVelocity: V = .zero, time: TimeInterval) -> V where V : VectorArithmetic
```

## 获取弹簧状态

- **value(fromValue:toValue:initialVelocity:time:)**：根据弹簧的初始位置和最终位置，计算弹簧在给定时间点的值。

- **velocity(target:initialVelocity:time:)**：根据目标变化量，计算弹簧在给定时间点的速度。

- **velocity(fromValue:toValue:initialVelocity:time:)**：根据弹簧的起始行程和结束行程，计算弹簧在给定时刻的速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/value(target:initialVelocity:time:)
crawled: 2025-12-01T11:04:07Z
---

# value(target:initialVelocity:time:)

**Instance Method**

Calculates the value of the spring at a given time given a target amount of change.

## Declaration

```swift
func value<V>(target: V, initialVelocity: V = .zero, time: TimeInterval) -> V where V : VectorArithmetic
```

## Getting spring state

- **value(fromValue:toValue:initialVelocity:time:)**: Calculates the value of the spring at a given time for a starting and ending value for the spring to travel.
- **velocity(target:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a target amount of change.
- **velocity(fromValue:toValue:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a starting and ending value for the spring to travel.

