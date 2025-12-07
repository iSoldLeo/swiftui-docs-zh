--- 来源：https://developer.apple.com/documentation/SwiftUI/RotateGesture3D/init(constrainedToAxis:minimumAngleDelta:)

抓取时间：2025-12-03T06:43:34Z

---

# init(constrainedToAxis:minimumAngleDelta:)

**Initializer**

创建一个旋转手势，并指定手势开始所需的最小角度增量以及用于约束旋转测量的轴。

## 声明

```swift
init(constrainedToAxis: RotationAxis3D? = nil, minimumAngleDelta: Angle = .degrees(1))
```

## 参数

- **constrainedToAxis**：旋转所围绕的 3D 轴。

- **minimumAngleDelta**：手势开始所需的最小角度增量。默认值为一度。

## 讨论

如果约束轴为 `nil`，则该手势测量的是无约束的 3D 旋转。

## 创建手势

- **minimumAngleDelta**：手势激活前的最小角度增量。

- **constrainedAxis**：旋转受限的轴。


---
source: https://developer.apple.com/documentation/SwiftUI/RotateGesture3D/init(constrainedToAxis:minimumAngleDelta:)
crawled: 2025-12-03T06:43:34Z
---

# init(constrainedToAxis:minimumAngleDelta:)

**Initializer**

Creates a rotation gesture with a minimum delta for the gesture to start and axis to constrain measurement of rotation.

## Declaration

```swift
init(constrainedToAxis: RotationAxis3D? = nil, minimumAngleDelta: Angle = .degrees(1))
```

## Parameters

- **constrainedToAxis**: The 3D axis about which rotation is measured.
- **minimumAngleDelta**: The minimum delta required before the gesture starts. The default value is a one-degree angle.

## Discussion

If the constrained axis is `nil`, the gesture measures unconstrained 3D rotation.

## Creating the gesture

- **minimumAngleDelta**: The minimum angle delta before the gesture becomes active.
- **constrainedAxis**: An axis around which the rotation is constrained.

