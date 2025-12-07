---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotation3DEffect(_:axis:anchor:)
抓取时间：2025-12-03T06:29:56Z
---

# rotation3DEffect(_:axis:anchor:)

**实例方法**

将内容围绕您指定为元素元组的轴旋转一个角度。

## 声明

```swift
func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint3D = .center) -> some VisualEffect

```

## 参数

- **angle**：旋转内容的角度。
- **axis**：旋转轴，以元组形式指定，三个空间维度的每个维度都有命名元素。
- **anchor**：内容中的单位点，围绕该点进行旋转。默认值为 [center](../UnitPoint3D/center.zh-Hans.md)。

## 返回值

旋转效果。

## 讨论



这种效果会使内容显示为旋转的，但不会改变内容的框架。以下代码使用内容中心的默认锚点，围绕 Y 轴旋转 45°：

```swift
Model3D(named: "robot")
    .visualEffect { content, geometryProxy in
        content
            .rotation3DEffect(.degrees(45), axis: (x: 0, y: 1, z: 0))
    }
```



```swift
Model3D(named: "robot")
    .rotation3DEffect(Rotation3D(.init(degrees: 45), axis: .y)
```

## 旋转

- **rotationEffect(_:anchor:)**：围绕指定点旋转二维内容。
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将内容渲染为围绕指定轴线的三维旋转。
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**：以三维方式围绕指定轴旋转渲染内容。
- **rotation3DEffect(_:anchor:)**：按指定的三维旋转值旋转内容。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotation3DEffect(_:axis:anchor:)
crawled: 2025-12-03T06:29:56Z
---

# rotation3DEffect(_:axis:anchor:)

**Instance Method**

Rotates content by an angle about an axis that you specify as a tuple of elements.

## Declaration

```swift
func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint3D = .center) -> some VisualEffect

```

## Parameters

- **angle**: The angle by which to rotate the content.
- **axis**: The axis of rotation, specified as a tuple with named elements for each of the three spatial dimensions.
- **anchor**: The unit point within the content about which to perform the rotation. The default value is [center](../UnitPoint3D/center.zh-Hans.md).

## Return Value

A rotation effect.

## Discussion



This effect causes the content to appear rotated, but doesn’t change the content’s frame. The following code applies a rotation of 45° about the y-axis, using the default anchor point at the center of the content:

```swift
Model3D(named: "robot")
    .visualEffect { content, geometryProxy in
        content
            .rotation3DEffect(.degrees(45), axis: (x: 0, y: 1, z: 0))
    }
```



```swift
Model3D(named: "robot")
    .rotation3DEffect(Rotation3D(.init(degrees: 45), axis: .y)
```

## Rotating

- **rotationEffect(_:anchor:)**: Rotates content in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates content by the specified 3D rotation value.

