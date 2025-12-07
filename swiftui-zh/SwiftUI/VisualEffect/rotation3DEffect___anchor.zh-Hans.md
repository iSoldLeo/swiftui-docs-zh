---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotation3DEffect(_:anchor:)
抓取时间： 2025-12-01T11:19:04Z
---

# rotation3DEffect(_:anchor:)

**实例方法**

按照指定的 3D 旋转值旋转内容。

## 声明

```swift
func rotation3DEffect(_ rotation: Rotation3D, anchor: UnitPoint3D = .center) -> some VisualEffect

```

## 参数

- **rotation**：要应用于内容的旋转。
- **anchor**：内容中要执行旋转的单位点。默认值为 [center](../UnitPoint3D/center.zh-Hans.md)。

## 返回值

旋转效果。

## 讨论

该特效会使内容显示为旋转的，但不会改变内容的框架。以下代码使用内容中心的默认锚点，围绕 Y 轴旋转 45°：

```swift
Model3D(named: "robot")
    .visualEffect { content, geometryProxy in
        content
            .rotation3DEffect(Rotation3D(angle: .degrees(45), axis: .y))
    }
```

在动画过程中，该修改器使用球形线性插值，可以产生更自然的动画，但不支持超过 360 度的旋转。要指定超过 360 度的角度，请考虑使用 `View/rotation3DEffect(_:axis:anchor:)-4enag`。

## 旋转

- **rotationEffect(_:anchor:)**：围绕指定点旋转二维内容。
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将内容渲染为围绕指定轴线的三维旋转。
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**：以三维方式围绕指定轴旋转渲染内容。
- **rotation3DEffect(_:axis:anchor:)**：以元素元组的形式将内容围绕指定的轴旋转一个角度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotation3DEffect(_:anchor:)
crawled: 2025-12-01T11:19:04Z
---

# rotation3DEffect(_:anchor:)

**Instance Method**

Rotates content by the specified 3D rotation value.

## Declaration

```swift
func rotation3DEffect(_ rotation: Rotation3D, anchor: UnitPoint3D = .center) -> some VisualEffect

```

## Parameters

- **rotation**: A rotation to apply to the content.
- **anchor**: The unit point within the content about which to perform the rotation. The default value is [center](../UnitPoint3D/center.zh-Hans.md).

## Return Value

A rotation effect.

## Discussion

This effect causes the content to appear rotated, but doesn’t change the content’s frame. The following code applies a rotation of 45° about the y-axis, using the default anchor point at the center of the content:

```swift
Model3D(named: "robot")
    .visualEffect { content, geometryProxy in
        content
            .rotation3DEffect(Rotation3D(angle: .degrees(45), axis: .y))
    }
```

During an animation, this modifier uses spherical linear interpolation, which produces more natural animations, but doesn’t support rotations over 360 degrees. To specify angles over 360 degrees, consider using `View/rotation3DEffect(_:axis:anchor:)-4enag`.

## Rotating

- **rotationEffect(_:anchor:)**: Rotates content in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:axis:anchor:)**: Rotates content by an angle about an axis that you specify as a tuple of elements.

