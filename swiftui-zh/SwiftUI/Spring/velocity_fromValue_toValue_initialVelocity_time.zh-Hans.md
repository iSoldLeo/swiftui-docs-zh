--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/velocity(fromValue:toValue:initialVelocity:time:)

抓取时间：2025-12-01T11:04:09Z

---

# velocity(fromValue:toValue:initialVelocity:time:)

**实例方法**

根据弹簧的起始值和结束值，计算弹簧在给定时间点的速度。

## 声明

```swift
func velocity<V>(fromValue: V, toValue: V, initialVelocity: V, time: TimeInterval) -> V where V : Animatable
```

## 获取弹簧状态

- **value(target:initialVelocity:time:)**：根据目标变化量，计算弹簧在给定时间点的值。

- **value(fromValue:toValue:initialVelocity:time:)**：根据弹簧的起始值和结束值，计算弹簧在给定时间点的值。

- **velocity(target:initialVelocity:time:)**：根据目标变化量，计算弹簧在给定时刻的速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/velocity(fromValue:toValue:initialVelocity:time:)
crawled: 2025-12-01T11:04:09Z
---

# velocity(fromValue:toValue:initialVelocity:time:)

**Instance Method**

Calculates the velocity of the spring at a given time given a starting and ending value for the spring to travel.

## Declaration

```swift
func velocity<V>(fromValue: V, toValue: V, initialVelocity: V, time: TimeInterval) -> V where V : Animatable
```

## Getting spring state

- **value(target:initialVelocity:time:)**: Calculates the value of the spring at a given time given a target amount of change.
- **value(fromValue:toValue:initialVelocity:time:)**: Calculates the value of the spring at a given time for a starting and ending value for the spring to travel.
- **velocity(target:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a target amount of change.

