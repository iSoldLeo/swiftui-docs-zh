---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/perspectiveRotationEffect(_:axis:anchor:perspective:)
抓取时间：2025-12-01T11:19:03Z
---

# perspectiveRotationEffect(_:axis:anchor:perspective:)

**实例方法**

将内容渲染为围绕指定轴线的三维旋转效果。

## 声明

```swift
func perspectiveRotationEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint3D = .back, perspective: CGFloat = 1) -> some VisualEffect

```

## 参数

- **angle**：旋转内容的角度。
- **axis**：旋转轴，以元组形式指定，三个空间维度的每个维度都有命名元素。
- **anchor**：内容中的一个单位点，围绕该点进行旋转。默认值为 [center](../UnitPoint3D/center.zh-Hans.md)。
- **perspective**：旋转的相对消失点。默认值为 `1`。

## 返回值

旋转效果。

## 讨论

使用此方法可创建围绕指定旋转轴的三维旋转效果。修改器会将二维内容投射到原始内容的平面上。使用`perspective` 输入来控制渲染器的消失点。下面的示例创建了文字绕 Y 轴旋转 45˚ 的外观：

```swift
Text("Rotation by passing an angle in degrees")
    .visualEffect { content, geometryProxy in
        content
            .perspectiveRotationEffect(
                .degrees(45),
                axis: (x: 0.0, y: 1.0, z: 0.0),
                anchor: .center,
                perspective: 1)
        }
    .border(Color.gray)
```





## 旋转

- **rotationEffect(_:anchor:)**：围绕指定点旋转二维内容。
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将内容渲染为围绕指定轴线的三维旋转。
- **rotation3DEffect(_:anchor:)**：按指定的三维旋转值旋转内容。
- **rotation3DEffect(_:axis:anchor:)**：以您指定为元素元组的轴为中心旋转内容一个角度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/perspectiveRotationEffect(_:axis:anchor:perspective:)
crawled: 2025-12-01T11:19:03Z
---

# perspectiveRotationEffect(_:axis:anchor:perspective:)

**Instance Method**

Renders content as if it’s rotated in three dimensions around the specified axis.

## Declaration

```swift
func perspectiveRotationEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint3D = .back, perspective: CGFloat = 1) -> some VisualEffect

```

## Parameters

- **angle**: The angle by which to rotate the content.
- **axis**: The axis of rotation, specified as a tuple with named elements for each of the three spatial dimensions.
- **anchor**: A unit point within the content about which to perform the rotation. The default value is [center](../UnitPoint3D/center.zh-Hans.md).
- **perspective**: The relative vanishing point for the rotation. The default is `1`.

## Return Value

A rotation effect.

## Discussion

Use this method to create the effect of rotating content in three dimensions around a specified axis of rotation. The modifier projects two dimensional content onto the original content’s plane. Use the `perspective` input to control the renderer’s vanishing point. The following example creates the appearance of rotating text 45˚ about the y-axis:

```swift
Text("Rotation by passing an angle in degrees")
    .visualEffect { content, geometryProxy in
        content
            .perspectiveRotationEffect(
                .degrees(45),
                axis: (x: 0.0, y: 1.0, z: 0.0),
                anchor: .center,
                perspective: 1)
        }
    .border(Color.gray)
```





## Rotating

- **rotationEffect(_:anchor:)**: Rotates content in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates content by an angle about an axis that you specify as a tuple of elements.

