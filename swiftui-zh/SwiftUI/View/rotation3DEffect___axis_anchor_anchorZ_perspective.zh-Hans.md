--- 来源：https://developer.apple.com/documentation/swiftui/view/rotation3deffect(_:axis:anchor:anchorz:perspective:)

抓取时间：2025-12-01T11:16:41Z

---

# rotation3DEffect(_:axis:anchor:anchorZ:perspective:)

**实例方法**

将视图内容渲染成绕指定轴在三维空间中旋转的效果。

## 声明

```swift
nonisolated func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint = .center, anchorZ: CGFloat = 0, perspective: CGFloat = 1) -> some View

```

## 参数

- **angle**：视图内容的旋转角度。

- **axis**：旋转轴，以元组形式指定，每个元组包含三个空间维度的命名元素。

- **anchor**：视图内用于旋转的二维单位点。默认值为 [center](../UnitPoint/center.zh-Hans.md)。

- **anchorZ**：Z 轴上用于旋转内容的坐标点。默认值为 `0`。

- **perspective**：旋转的相对消失点。默认值为 `1`。

## 返回值

包含旋转内容的视图。

## 说明

使用此方法可创建围绕指定旋转轴在三维空间中旋转视图的效果。该修改器会将旋转后的内容投影到原始视图的平面上。使用 `perspective` 值控制渲染器的消失点。以下示例创建文本绕 y 轴旋转 45° 的效果：

```swift
Text("Rotation by passing an angle in degrees")
    .rotation3DEffect(
        .degrees(45),
        axis: (x: 0.0, y: 1.0, z: 0.0),
        anchor: .center,
        anchorZ: 0,
        perspective: 1)
    .border(Color.gray)
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：按指定的 3D 旋转值旋转视图内容。

- **rotation3DEffect(_:axis:anchor:)**：围绕您以元素元组形式指定的轴旋转一定角度，使视图内容旋转。

- **transformEffect(_:)**：对该视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对该视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对该视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/swiftui/view/rotation3deffect(_:axis:anchor:anchorz:perspective:)
crawled: 2025-12-01T11:16:41Z
---

# rotation3DEffect(_:axis:anchor:anchorZ:perspective:)

**Instance Method**

Renders a view’s content as if it’s rotated in three dimensions around the specified axis.

## Declaration

```swift
nonisolated func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint = .center, anchorZ: CGFloat = 0, perspective: CGFloat = 1) -> some View

```

## Parameters

- **angle**: The angle by which to rotate the view’s content.
- **axis**: The axis of rotation, specified as a tuple with named elements for each of the three spatial dimensions.
- **anchor**: A two dimensional unit point within the view about which to perform the rotation. The default value is [center](../UnitPoint/center.zh-Hans.md).
- **anchorZ**: The location on the z-axis around which to rotate the content. The default is `0`.
- **perspective**: The relative vanishing point for the rotation. The default is `1`.

## Return Value

A view with rotated content.

## Discussion

Use this method to create the effect of rotating a view in three dimensions around a specified axis of rotation. The modifier projects the rotated content onto the original view’s plane. Use the `perspective` value to control the renderer’s vanishing point. The following example creates the appearance of rotating text 45˚ about the y-axis:

```swift
Text("Rotation by passing an angle in degrees")
    .rotation3DEffect(
        .degrees(45),
        axis: (x: 0.0, y: 1.0, z: 0.0),
        anchor: .center,
        anchorZ: 0,
        perspective: 1)
    .border(Color.gray)
```





## Scaling, rotating, or transforming a view

- **scaledToFill()**: Scales this view to fill its parent.
- **scaledToFit()**: Scales this view to fit its parent.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales this view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.
- **aspectRatio(_:contentMode:)**: Constrains this view’s dimensions to the specified aspect ratio.
- **rotationEffect(_:anchor:)**: Rotates a view’s rendered output in two dimensions around the specified point.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

