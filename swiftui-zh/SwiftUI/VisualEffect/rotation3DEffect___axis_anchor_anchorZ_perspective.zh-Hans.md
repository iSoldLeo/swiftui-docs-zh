---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotation3DEffect(_:axis:anchor:anchorZ:perspective:)
抓取时间：2025-12-01T11:19:02Z
---

# rotation3DEffect(_:axis:anchor:anchorZ:perspective:)

**实例方法**

以围绕指定轴线进行三维旋转的方式渲染内容。

## 声明

```swift
func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint = .center, anchorZ: CGFloat = 0, perspective: CGFloat = 1) -> some VisualEffect

```

## 参数

- **angle**：旋转内容的角度。
- **axis**：旋转轴，以元组形式指定，三个空间维度的每个维度都有命名元素。
- **anchor**：内容中的二维单位点，围绕该点进行旋转。默认值为 [center](../UnitPoint/center.zh-Hans.md)。
- **anchorZ**：要旋转内容的 Z 轴位置。默认值为 `0`。
- **perspective**：旋转的相对消失点。默认值为 `1`。

## 返回值

旋转效果。

## 讨论

使用此方法可创建围绕指定旋转轴在三维空间中旋转二维视图的效果。该效果会将旋转后的内容投射到原始内容的平面上。使用`perspective` 输入来控制渲染器的消失点。下面的示例创建了文字绕 y 轴旋转 45˚ 的外观：

```swift
Text("Rotation by passing an angle in degrees")
    .visualEffect { content, geometryProxy in
        content
            .rotation3DEffect(
                .degrees(45),
                axis: (x: 0.0, y: 1.0, z: 0.0),
                anchor: .center,
                anchorZ: 0,
                perspective: 1)
        }
    .border(Color.gray)
```





## 旋转

- **rotationEffect(_:anchor:)**：围绕指定点旋转二维内容。
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**：将内容渲染为围绕指定轴线的三维旋转。
- **rotation3DEffect(_:anchor:)**：按指定的三维旋转值旋转内容。
- **rotation3DEffect(_:axis:anchor:)**：以您指定为元素元组的轴为中心旋转内容一个角度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotation3DEffect(_:axis:anchor:anchorZ:perspective:)
crawled: 2025-12-01T11:19:02Z
---

# rotation3DEffect(_:axis:anchor:anchorZ:perspective:)

**Instance Method**

Renders content as if it’s rotated in three dimensions around the specified axis.

## Declaration

```swift
func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint = .center, anchorZ: CGFloat = 0, perspective: CGFloat = 1) -> some VisualEffect

```

## Parameters

- **angle**: The angle by which to rotate the content.
- **axis**: The axis of rotation, specified as a tuple with named elements for each of the three spatial dimensions.
- **anchor**: A two dimensional unit point within the content about which to perform the rotation. The default value is [center](../UnitPoint/center.zh-Hans.md).
- **anchorZ**: The location on the z-axis around which to rotate the content. The default is `0`.
- **perspective**: The relative vanishing point for the rotation. The default is `1`.

## Return Value

A rotation effect.

## Discussion

Use this method to create the effect of rotating a two dimensional view in three dimensions around a specified axis of rotation. The effect projects the rotated content onto the original content’s plane. Use the `perspective` input to control the renderer’s vanishing point. The following example creates the appearance of rotating text 45˚ about the y-axis:

```swift
Text("Rotation by passing an angle in degrees")
    .visualEffect { content, geometryProxy in
        content
            .rotation3DEffect(
                .degrees(45),
                axis: (x: 0.0, y: 1.0, z: 0.0),
                anchor: .center,
                anchorZ: 0,
                perspective: 1)
        }
    .border(Color.gray)
```





## Rotating

- **rotationEffect(_:anchor:)**: Rotates content in two dimensions around the specified point.
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates content by an angle about an axis that you specify as a tuple of elements.

