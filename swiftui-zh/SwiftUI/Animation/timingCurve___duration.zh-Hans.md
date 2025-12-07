---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/timingCurve(_:duration:)
抓取时间： 2025-12-03T06:12:22Z
---

# TimingCurve(_:duration:)

**类型方法**

创建一个新动画，速度由给定的曲线控制。

## 声明

```swift
static func timingCurve(_ curve: UnitCurve, duration: TimeInterval) -> Animation
```

## 参数

- **duration**：动画的持续时间，以秒为单位。

## 创建自定义动画

- **init(_:)**：创建包含指定自定义动画的`Animation`。
- **timingCurve(_:_:_:_:duration:)**：由立方贝塞尔定时曲线创建的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/timingCurve(_:duration:)
crawled: 2025-12-03T06:12:22Z
---

# timingCurve(_:duration:)

**Type Method**

Creates a new animation with speed controlled by the given curve.

## Declaration

```swift
static func timingCurve(_ curve: UnitCurve, duration: TimeInterval) -> Animation
```

## Parameters

- **duration**: The duration of the animation, in seconds.

## Creating custom animations

- **init(_:)**: Create an `Animation` that contains the specified custom animation.
- **timingCurve(_:_:_:_:duration:)**: An animation created from a cubic Bézier timing curve.

