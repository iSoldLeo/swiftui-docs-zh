--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/value(fromValue:toValue:initialVelocity:time:)

抓取时间：2025-12-01T11:04:08Z

---

# value(fromValue:toValue:initialVelocity:time:)

**实例方法**

计算给定弹簧初始值和最终行程值时，弹簧在给定时间的数值。

## 声明

```swift
func value<V>(fromValue: V, toValue: V, initialVelocity: V, time: TimeInterval) -> V where V : Animatable
```

## 获取弹簧状态

- **value(target:initialVelocity:time:)**：计算给定目标变化量时，弹簧在给定时间的数值。

- **velocity(target:initialVelocity:time:)**：计算给定目标变化量时，弹簧在给定时间的速度。

- **velocity(fromValue:toValue:initialVelocity:time:)**：根据弹簧的起始行程和结束行程，计算弹簧在给定时刻的速度。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/value(fromValue:toValue:initialVelocity:time:)
crawled: 2025-12-01T11:04:08Z
---

# value(fromValue:toValue:initialVelocity:time:)

**Instance Method**

Calculates the value of the spring at a given time for a starting and ending value for the spring to travel.

## Declaration

```swift
func value<V>(fromValue: V, toValue: V, initialVelocity: V, time: TimeInterval) -> V where V : Animatable
```

## Getting spring state

- **value(target:initialVelocity:time:)**: Calculates the value of the spring at a given time given a target amount of change.
- **velocity(target:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a target amount of change.
- **velocity(fromValue:toValue:initialVelocity:time:)**: Calculates the velocity of the spring at a given time given a starting and ending value for the spring to travel.

