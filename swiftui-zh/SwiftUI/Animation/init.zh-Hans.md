---
来源： https://developer.apple.com/documentation/SwiftUI/Animation/init(_:)
抓取时间： 2025-12-03T06:12:21Z
---

# init(_:)

**Initializer**

创建包含指定自定义动画的`Animation`。

## 声明

```swift
init<A>(_ base: A) where A : CustomAnimation
```

## 创建自定义动画

- **timingCurve(_:duration:)**：创建一个新动画，速度由给定的曲线控制。
- **timingCurve(_:_:_:_:duration:)**：由立方贝塞尔定时曲线创建的动画。


---
source: https://developer.apple.com/documentation/SwiftUI/Animation/init(_:)
crawled: 2025-12-03T06:12:21Z
---

# init(_:)

**Initializer**

Create an `Animation` that contains the specified custom animation.

## Declaration

```swift
init<A>(_ base: A) where A : CustomAnimation
```

## Creating custom animations

- **timingCurve(_:duration:)**: Creates a new animation with speed controlled by the given curve.
- **timingCurve(_:_:_:_:duration:)**: An animation created from a cubic Bézier timing curve.

