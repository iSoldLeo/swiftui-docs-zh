--- 来源：https://developer.apple.com/documentation/SwiftUI/View/rotation3DLayout(_:)

抓取时间：2025-11-30T19:49:43Z

---

# rotation3DLayout(_:)

**实例方法**

旋转视图，并对其在包含布局中的 frame 进行相应调整

## 声明

```swift
nonisolated func rotation3DLayout(_ rotation: Rotation3D) -> some View

```

## 参数

- **rotation**：要应用于视图及其 frame 的旋转角度。

## 说明

以下示例将顶层平面旋转 45 度，并调整其 frame 以适应此旋转。VStack 的大小将根据旋转后和标准模型进行调整。

```swift
VStack {
    Model3D(named: "plane")
        .rotation3DLayout(Rotation3D(angle: .degrees(45), axis: .z))
    Model3D(named: "plane")
```

}

布局系统将使用一个完全包含旋转视图的边界框，这意味着此修改器可以改变其应用视图的大小。


---
source: https://developer.apple.com/documentation/SwiftUI/View/rotation3DLayout(_:)
crawled: 2025-11-30T19:49:43Z
---

# rotation3DLayout(_:)

**Instance Method**

Rotates a view with impacts to its frame in a containing layout

## Declaration

```swift
nonisolated func rotation3DLayout(_ rotation: Rotation3D) -> some View

```

## Parameters

- **rotation**: A rotation to apply to the view and its frame.

## Discussion

The following example will rotate the top plane by 45 degrees while adjusting its frame to account for this rotation. The VStack sizes to fit the rotated and standard models.

```swift
VStack {
    Model3D(named: "plane")
        .rotation3DLayout(Rotation3D(angle: .degrees(45), axis: .z))
    Model3D(named: "plane")
```

}

The layout system will use a bounding box that completely contains the rotated view, meaning this modifier can change the size of the view it is applied to.

