--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scaleEffect(x:y:z:anchor:)

抓取时间：2025-12-02T17:37:08Z

---

# scaleEffect(x:y:z:anchor:)

**实例方法**

根据指定的水平、垂直和深度因子，相对于锚点缩放此视图。

## 声明

```swift
nonisolated func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, z: CGFloat = 1.0, anchor: UnitPoint3D = .center) -> some View

```

## 参数

- **x**：此视图的水平缩放因子。

- **y**：此视图的垂直缩放因子。

- **z**：此视图的深度缩放因子。

- **anchor**：用于缩放视图的锚点。默认居中。

## 返回值

返回一个视图，该视图按 `x`、`y` 和 `z` 缩放。

## 说明

缩放内容不会改变视图的原始尺寸。要更改视图的尺寸，请改用 `frame()` 之类的修饰符。

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的缩放比例在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容按指定的 3D 旋转值旋转。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的轴（以元素元组形式表示）旋转一定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用 3D 变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/SwiftUI/View/scaleEffect(x:y:z:anchor:)
crawled: 2025-12-02T17:37:08Z
---

# scaleEffect(x:y:z:anchor:)

**Instance Method**

Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.

## Declaration

```swift
nonisolated func scaleEffect(x: CGFloat = 1.0, y: CGFloat = 1.0, z: CGFloat = 1.0, anchor: UnitPoint3D = .center) -> some View

```

## Parameters

- **x**: The horizontal scale factor for this view.
- **y**: The vertical scale factor for this view.
- **z**: The depth scale factor for this view.
- **anchor**: The anchor point about which to scale the view. Defaults to center.

## Return Value

A view that scales this view by `x`,`y`, and `z`.

## Discussion

The original dimensions of the view are considered to be unchanged by scaling the contents. To change the dimensions of the view, use a modifier like `frame()` instead.

## Scaling, rotating, or transforming a view

- **scaledToFill()**: Scales this view to fill its parent.
- **scaledToFit()**: Scales this view to fit its parent.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales this view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **aspectRatio(_:contentMode:)**: Constrains this view’s dimensions to the specified aspect ratio.
- **rotationEffect(_:anchor:)**: Rotates a view’s rendered output in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

