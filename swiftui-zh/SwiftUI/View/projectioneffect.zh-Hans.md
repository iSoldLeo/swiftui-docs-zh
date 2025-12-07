--- 来源：https://developer.apple.com/documentation/swiftui/view/projectioneffect(_:)

抓取时间：2025-12-01T11:16:46Z

---

# projectionEffect(_:)

**实例方法**

将投影变换应用于此视图的渲染输出。

## 声明

```swift
nonisolated func projectionEffect(_ transform: ProjectionTransform) -> some View

```

## 参数

- **transform**：要应用于视图的 [ProjectionTransform](../ProjectionTransform.zh-Hans.md)。

## 说明

使用 `projectionEffect(_:)` 将 3D 变换应用于视图。

以下示例将文本绕 `z` 轴（即指向屏幕外的轴）旋转 30°：

```swift
// This transform represents a 30˚ rotation around the z axis.
let transform = CATransform3DMakeRotation(
    -30 * (.pi / 180), 0.0, 0.0, 1.0)

Text("Projection effects using transforms")
    .projectionEffect(.init(transform))
    .border(Color.gray)
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的缩放比例在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的缩放比例在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容按指定的 3D 旋转值旋转。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的轴（以元素元组形式表示）旋转一定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用 3D 变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/swiftui/view/projectioneffect(_:)
crawled: 2025-12-01T11:16:46Z
---

# projectionEffect(_:)

**Instance Method**

Applies a projection transformation to this view’s rendered output.

## Declaration

```swift
nonisolated func projectionEffect(_ transform: ProjectionTransform) -> some View

```

## Parameters

- **transform**: A [ProjectionTransform](../ProjectionTransform.zh-Hans.md) to apply to the view.

## Discussion

Use `projectionEffect(_:)` to apply a 3D transformation to the view.

The example below rotates the text 30˚ around the `z` axis, which is the axis pointing out of the screen:

```swift
// This transform represents a 30˚ rotation around the z axis.
let transform = CATransform3DMakeRotation(
    -30 * (.pi / 180), 0.0, 0.0, 1.0)

Text("Projection effects using transforms")
    .projectionEffect(.init(transform))
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
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **ProjectionTransform**

