--- 来源：https://developer.apple.com/documentation/swiftui/view/rotationeffect(_:anchor:)

抓取时间：2025-12-03T06:27:31Z

---

# rotationEffect(_:anchor:)

**实例方法**

围绕指定点在二维空间中旋转视图的渲染输出。

## 声明

```swift
nonisolated func rotationEffect(_ angle: Angle, anchor: UnitPoint = .center) -> some View

```

## 参数

- **angle**：视图旋转的角度。

- **anchor**：视图中用于旋转的单位点。默认值为 [center](../UnitPoint/center.zh-Hans.md)。

## 返回值

旋转后的视图。

## 讨论

此修改器会将视图内容绕着指向 xy 平面外的轴旋转。它不会影响视图的框架。以下代码将文本旋转 22°，然后在修改后的视图周围绘制边框，以表明旋转修改器不会改变视图的框架：

```swift
Text("Rotation by passing an angle in degrees")
    .rotationEffect(.degrees(22))
    .border(Color.gray)
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染为绕指定轴在三维空间中旋转后的效果。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染为绕指定轴在三维空间中旋转后的效果。

- **rotation3DEffect(_:anchor:)**：将视图内容旋转指定的三维旋转值。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的轴（以元素元组形式表示）旋转一定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/swiftui/view/rotationeffect(_:anchor:)
crawled: 2025-12-03T06:27:31Z
---

# rotationEffect(_:anchor:)

**Instance Method**

Rotates a view’s rendered output in two dimensions around the specified point.

## Declaration

```swift
nonisolated func rotationEffect(_ angle: Angle, anchor: UnitPoint = .center) -> some View

```

## Parameters

- **angle**: The angle by which to rotate the view.
- **anchor**: A unit point within the view about which to perform the rotation. The default value is [center](../UnitPoint/center.zh-Hans.md).

## Return Value

A view with rotated content.

## Discussion

This modifier rotates the view’s content around the axis that points out of the xy-plane. It has no effect on the view’s frame. The following code rotates text by 22˚ and then draws a border around the modified view to show that the frame remains unchanged by the rotation modifier:

```swift
Text("Rotation by passing an angle in degrees")
    .rotationEffect(.degrees(22))
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
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

