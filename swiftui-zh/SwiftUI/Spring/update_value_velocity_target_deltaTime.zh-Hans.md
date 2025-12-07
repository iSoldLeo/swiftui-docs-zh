--- 来源：https://developer.apple.com/documentation/SwiftUI/Spring/update(value:velocity:target:deltaTime:)

抓取时间：2025-12-03T06:15:02Z

---

# update(value:velocity:target:deltaTime:)

**实例方法**

更新弹簧的当前值和速度。

## 声明

```swift
func update<V>(value: inout V, velocity: inout V, target: V, deltaTime: TimeInterval) where V : VectorArithmetic
```

## 参数

- **value**：弹簧的当前值。

- **velocity**：弹簧的当前速度。

- **target**：弹簧`value`运动的目标位置。

- **deltaTime**：自弹簧位于`value`指定位置以来所经过的时间。


---
source: https://developer.apple.com/documentation/SwiftUI/Spring/update(value:velocity:target:deltaTime:)
crawled: 2025-12-03T06:15:02Z
---

# update(value:velocity:target:deltaTime:)

**Instance Method**

Updates the current  value and velocity of a spring.

## Declaration

```swift
func update<V>(value: inout V, velocity: inout V, target: V, deltaTime: TimeInterval) where V : VectorArithmetic
```

## Parameters

- **value**: The current value of the spring.
- **velocity**: The current velocity of the spring.
- **target**: The target that `value` is moving towards.
- **deltaTime**: The amount of time that has passed since the spring was at the position specified by `value`.

