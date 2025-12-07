--- 来源：https://developer.apple.com/documentation/SwiftUI/View/rotation3DLayout(_:axis:)

抓取时间：2025-11-30T21:10:20Z

---

# rotation3DLayout(_:axis:)

**实例方法**

旋转视图，并对其框架（frame）进行调整。

## 声明

```swift
nonisolated func rotation3DLayout(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat)) -> some View

```

## 参数

- **angle**：视图及其框架的旋转角度。

- **axis**：旋转轴。

## 说明

以下示例将顶层平面旋转 45 度，并调整其框架以适应此旋转。VStack 的大小将根据旋转后的模型和标准模型进行调整。

```swift
VStack {
    Model3D(named: "plane")
        .rotation3DLayout(.degrees(45), axis: (x: 0, y: 0, z: 1))
    Model3D(named: "plane")
```

}

布局系统将使用一个完全包含旋转视图的边界框，这意味着此修改器可以改变其应用视图的大小。


---
source: https://developer.apple.com/documentation/SwiftUI/View/rotation3DLayout(_:axis:)
crawled: 2025-11-30T21:10:20Z
---

# rotation3DLayout(_:axis:)

**Instance Method**

Rotates a view with impacts to its frame in a containing layout

## Declaration

```swift
nonisolated func rotation3DLayout(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat)) -> some View

```

## Parameters

- **angle**: The angle by which to rotate the view and its frame.
- **axis**: The axis of rotation.

## Discussion

The following example will rotate the top plane by 45 degrees while adjusting its frame to account for this rotation. The VStack sizes to fit the rotated and standard models.

```swift
VStack {
    Model3D(named: "plane")
        .rotation3DLayout(.degrees(45), axis: (x: 0, y: 0, z: 1))
    Model3D(named: "plane")
```

}

The layout system will use a bounding box that completely contains the rotated view, meaning this modifier can change the size of the view it is applied to.

