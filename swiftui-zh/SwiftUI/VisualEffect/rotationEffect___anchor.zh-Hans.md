---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotationEffect(_:anchor:)
抓取时间： 2025-12-01T11:19:01Z
---

# rotationEffect(_:anchor:)

**实例方法**

围绕指定点从两个维度旋转内容。

## 声明

```swift
func rotationEffect(_ angle: Angle, anchor: UnitPoint = .center) -> some VisualEffect

```

## 参数

- **angle**：旋转内容的角度。
- **anchor**：内容中的一个单位点，围绕该点进行旋转。默认值为 [center](../UnitPoint/center.zh-Hans.md)。

## 返回值

旋转效果。

## 讨论

该特效会使内容绕着 xy 平面外的轴线旋转。它对内容的框架没有影响。以下代码将文本旋转 22˚，然后在修改后的视图周围绘制边框，以显示边框在旋转后保持不变：

```swift
Text("Rotation by passing an angle in degrees")
    .visualEffect { content, geometryProxy in
        content
            .rotationEffect(.degrees(22))
    }
    .border(Color.gray)
```



## 旋转

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：围绕指定轴以三维旋转的方式渲染内容。
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**：以三维方式围绕指定轴旋转渲染内容。
- **rotation3DEffect(_:anchor:)**：按指定的三维旋转值旋转内容。
- **rotation3DEffect(_:axis:anchor:)**：以您指定为元素元组的轴为中心旋转内容一个角度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/rotationEffect(_:anchor:)
crawled: 2025-12-01T11:19:01Z
---

# rotationEffect(_:anchor:)

**Instance Method**

Rotates content in two dimensions around the specified point.

## Declaration

```swift
func rotationEffect(_ angle: Angle, anchor: UnitPoint = .center) -> some VisualEffect

```

## Parameters

- **angle**: The angle by which to rotate the content.
- **anchor**: A unit point within the content about which to perform the rotation. The default value is [center](../UnitPoint/center.zh-Hans.md).

## Return Value

A rotation effect.

## Discussion

This effect rotates the content around the axis that points out of the xy-plane. It has no effect on the content’s frame. The following code rotates text by 22˚ and then draws a border around the modified view to show that the frame remains unchanged by the rotation:

```swift
Text("Rotation by passing an angle in degrees")
    .visualEffect { content, geometryProxy in
        content
            .rotationEffect(.degrees(22))
    }
    .border(Color.gray)
```



## Rotating

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates content by an angle about an axis that you specify as a tuple of elements.

