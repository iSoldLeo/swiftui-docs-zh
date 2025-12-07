--- 来源：https://developer.apple.com/documentation/SwiftUI/RotateGesture3D/constrainedAxis
抓取时间：2025-12-03T06:43:36Z

---

# constrainedAxis

**实例属性**

旋转受限的轴。

## 声明

```swift
var constrainedAxis: RotationAxis3D?
```

## 说明

如果轴为 `nil`，则旋转不受约束。

## 创建手势

- **init(constrainedToAxis:minimumAngleDelta:)**：创建一个旋转手势，并指定手势开始的最小角度增量和用于约束旋转角度的轴。

- **minimumAngleDelta**：手势激活前的最小角度增量。


---
source: https://developer.apple.com/documentation/SwiftUI/RotateGesture3D/constrainedAxis
crawled: 2025-12-03T06:43:36Z
---

# constrainedAxis

**Instance Property**

An axis around which the rotation is constrained.

## Declaration

```swift
var constrainedAxis: RotationAxis3D?
```

## Discussion

If the axis is `nil`, the rotation is unconstrained.

## Creating the gesture

- **init(constrainedToAxis:minimumAngleDelta:)**: Creates a rotation gesture with a minimum delta for the gesture to start and axis to constrain measurement of rotation.
- **minimumAngleDelta**: The minimum angle delta before the gesture becomes active.

