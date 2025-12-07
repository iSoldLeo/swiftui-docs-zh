--- 来源：https://developer.apple.com/documentation/SwiftUI/CubicKeyframe/init(_:duration:startVelocity:endVelocity:)

抓取时间：2025-12-01T11:03:36Z

---

# init(_:duration:startVelocity:endVelocity:)

**Initializer**

使用给定的值和时间戳创建一个新的关键帧。

## 声明

```swift
init(_ to: Value, duration: TimeInterval, startVelocity: Value? = nil, endVelocity: Value? = nil)
```

## 参数

- **to**：关键帧的值。

- **duration**：此关键帧定义的片段的持续时间。

- **startVelocity**：线段起始位置的值的速度，或者使用 `nil` 自动计算速度以保持平滑运动。

- **endVelocity**：线段结束位置的值的速度，或者使用 `nil` 自动计算速度以保持平滑运动。


---
source: https://developer.apple.com/documentation/SwiftUI/CubicKeyframe/init(_:duration:startVelocity:endVelocity:)
crawled: 2025-12-01T11:03:36Z
---

# init(_:duration:startVelocity:endVelocity:)

**Initializer**

Creates a new keyframe using the given value and timestamp.

## Declaration

```swift
init(_ to: Value, duration: TimeInterval, startVelocity: Value? = nil, endVelocity: Value? = nil)
```

## Parameters

- **to**: The value of the keyframe.
- **duration**: The duration of the segment defined by this keyframe.
- **startVelocity**: The velocity of the value at the beginning of the segment, or `nil` to automatically compute the velocity to maintain smooth motion.
- **endVelocity**: The velocity of the value at the end of the segment, or `nil` to automatically compute the velocity to maintain smooth motion.

