--- 来源：https://developer.apple.com/documentation/SwiftUI/View/transform3DEffect(_:)

抓取时间：2025-12-02T17:37:14Z

---

# transform3DEffect(_:)

**实例方法**

将 3D 变换应用于此视图的渲染输出。

## 声明

```swift
nonisolated func transform3DEffect(_ transform: AffineTransform3D) -> some View

```

## 参数

- **transform**：要应用于视图的 3D 变换，将其解释为空间中的 3D 平面。

## 返回值

根据提供的 `transform` 进行变换后渲染的视图。

### 围绕锚点应用变换

此方法不会相对于锚点调整变换。请改用 [scaleEffect(_:anchor:)](scaleEffect___anchor.zh-Hans.md) 和 [rotation3DEffect(_:anchor:)](rotation3DEffect___anchor.zh-Hans.md) 分别应用缩放和旋转。

```swift
Model3D(url: URL(string: "https://example.com/robot.usdz")!)
   .scaleEffect(transform.scale)
   .rotation3DEffect(transform.rotation ?? .identity)
   .transform3DEffect(AffineTransform3D(
       translation: transform.translation))
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容按指定的 3D 旋转值旋转。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的轴（以元素元组形式表示）旋转一定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/SwiftUI/View/transform3DEffect(_:)
crawled: 2025-12-02T17:37:14Z
---

# transform3DEffect(_:)

**Instance Method**

Applies a 3D transformation to this view’s rendered output.

## Declaration

```swift
nonisolated func transform3DEffect(_ transform: AffineTransform3D) -> some View

```

## Parameters

- **transform**: The 3D transformation to apply to the view, interpreting it as a 3D plane in space.

## Return Value

A view that renders transformed according to the provided `transform`

### Apply a transform about an anchor

This does not adjust the transform relative to an anchor point. Instead, apply the scale and rotation separately using [scaleEffect(_:anchor:)](scaleEffect___anchor.zh-Hans.md) together with [rotation3DEffect(_:anchor:)](rotation3DEffect___anchor.zh-Hans.md).

```swift
Model3D(url: URL(string: "https://example.com/robot.usdz")!)
   .scaleEffect(transform.scale)
   .rotation3DEffect(transform.rotation ?? .identity)
   .transform3DEffect(AffineTransform3D(
       translation: transform.translation))
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
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

