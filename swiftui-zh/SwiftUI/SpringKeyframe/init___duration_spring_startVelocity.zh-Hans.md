--- 来源：https://developer.apple.com/documentation/SwiftUI/SpringKeyframe/init(_:duration:spring:startVelocity:)

抓取时间：2025-12-03T06:14:30Z

---

# init(_:duration:spring:startVelocity:)

**Initializer**

使用给定的值和时间戳创建一个新的关键帧。

## 声明

```swift
init(_ to: Value, duration: TimeInterval? = nil, spring: Spring = Spring(), startVelocity: Value? = nil)
```

## 参数

- **to**：关键帧的值。

- **duration**：此关键帧定义的片段的持续时间，如果为 nil 则使用弹簧的稳定持续时间。

- **spring**：定义此关键帧之前线段形状的弹簧

- **startVelocity**：线段起始位置的速度值，或者使用 `nil` 自动计算速度以保持平滑运动。


---
source: https://developer.apple.com/documentation/SwiftUI/SpringKeyframe/init(_:duration:spring:startVelocity:)
crawled: 2025-12-03T06:14:30Z
---

# init(_:duration:spring:startVelocity:)

**Initializer**

Creates a new keyframe using the given value and timestamp.

## Declaration

```swift
init(_ to: Value, duration: TimeInterval? = nil, spring: Spring = Spring(), startVelocity: Value? = nil)
```

## Parameters

- **to**: The value of the keyframe.
- **duration**: The duration of the segment defined by this keyframe, or nil to use the settling duration of the spring.
- **spring**: The spring that defines the shape of the segment befire this keyframe
- **startVelocity**: The velocity of the value at the start of the segment, or `nil` to automatically compute the velocity to maintain smooth motion.

