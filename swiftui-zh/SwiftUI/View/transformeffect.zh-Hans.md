--- 来源：https://developer.apple.com/documentation/swiftui/view/transformeffect(_:)

抓取时间：2025-12-03T06:27:36Z

---

# transformEffect(_:)

**实例方法**

对当前视图的渲染输出应用仿射变换。

## 声明

```swift
nonisolated func transformEffect(_ transform: CGAffineTransform) -> some View

```

## 参数

- **transform**：要应用于视图的 [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform]。

## 说明

使用 `transformEffect(_:)` 根据提供的 [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform] 旋转、缩放、平移或倾斜视图的输出。

在以下示例中，文本绕 `y` 轴旋转了 -30°。

```swift
let transform = CGAffineTransform(rotationAngle: -30 * (.pi / 180))

Text("Projection effect using transforms")
    .transformEffect(transform)
    .border(Color.gray)
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直量缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染为围绕指定轴在三维空间中旋转。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染为围绕指定轴在三维空间中旋转。

- **rotation3DEffect(_:anchor:)**：按指定的 3D 旋转值旋转视图内容。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的轴（以元素元组形式表示）旋转一定角度。

- **transform3DEffect(_:)**：对视图的渲染输出应用 3D 变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/swiftui/view/transformeffect(_:)
crawled: 2025-12-03T06:27:36Z
---

# transformEffect(_:)

**Instance Method**

Applies an affine transformation to this view’s rendered output.

## Declaration

```swift
nonisolated func transformEffect(_ transform: CGAffineTransform) -> some View

```

## Parameters

- **transform**: A [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform] to apply to the view.

## Discussion

Use `transformEffect(_:)` to rotate, scale, translate, or skew the output of the view according to the provided [doc://com.apple.documentation/documentation/CoreFoundation/CGAffineTransform].

In the example below, the text is rotated at -30˚ on the `y` axis.

```swift
let transform = CGAffineTransform(rotationAngle: -30 * (.pi / 180))

Text("Projection effect using transforms")
    .transformEffect(transform)
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
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

