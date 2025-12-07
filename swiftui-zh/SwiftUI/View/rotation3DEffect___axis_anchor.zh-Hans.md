--- 来源：https://developer.apple.com/documentation/swiftui/view/rotation3deffect(_:axis:anchor:)

抓取时间：2025-12-03T06:27:35Z

---

# rotation3DEffect(_:axis:anchor:)

**实例方法**

将视图内容绕您指定的轴旋转一定角度，该轴由一个元素元组表示。

## 声明

```swift
nonisolated func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint3D = .center) -> some View

```

## 参数

- **angle**：视图内容的旋转角度。

- **axis**：旋转轴，由一个元组表示，每个元组包含三个空间维度的命名元素。

- **anchor**：视图中用于旋转的单位点。默认值为 [center](../UnitPoint3D/center.zh-Hans.md)。

## 返回值

旋转后的视图。

## 说明

此修改器旋转视图内容，但不改变视图的框架。以下代码使用视图中心的默认锚点，显示一个绕 y 轴旋转 45° 的 3D 模型：

```swift
Model3D(named: "robot")
    .rotation3DEffect(.degrees(45), axis: (x: 0, y: 1, z: 0))
```

```swift
let rotation = Rotation3D(
    .init(degrees: 45), axis: RotationAxis3D(x: 0, y: 1, z: 0))
Model3D(named: "robot")
    .rotation3DEffect(rotation)
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的缩放比例，在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直缩放比例，缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点，在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成绕指定轴旋转三维后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容旋转指定的三维旋转值。

- **transformEffect(_:)**：对该视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对该视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对该视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/swiftui/view/rotation3deffect(_:axis:anchor:)
crawled: 2025-12-03T06:27:35Z
---

# rotation3DEffect(_:axis:anchor:)

**Instance Method**

Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.

## Declaration

```swift
nonisolated func rotation3DEffect(_ angle: Angle, axis: (x: CGFloat, y: CGFloat, z: CGFloat), anchor: UnitPoint3D = .center) -> some View

```

## Parameters

- **angle**: The angle by which to rotate the view’s content.
- **axis**: The axis of rotation, specified as a tuple with named elements for each of the three spatial dimensions.
- **anchor**: The unit point within the view about which to perform the rotation. The default value is [center](../UnitPoint3D/center.zh-Hans.md).

## Return Value

A view with rotated content.

## Discussion



This modifier rotates the view’s content without changing the view’s frame. The following code displays a 3D model with a rotation of 45° about the y-axis using the default anchor point at the center of the view:

```swift
Model3D(named: "robot")
    .rotation3DEffect(.degrees(45), axis: (x: 0, y: 1, z: 0))
```



```swift
let rotation = Rotation3D(
    .init(degrees: 45), axis: RotationAxis3D(x: 0, y: 1, z: 0))
Model3D(named: "robot")
    .rotation3DEffect(rotation)
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
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

