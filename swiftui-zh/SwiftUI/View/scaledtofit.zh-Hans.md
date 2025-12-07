--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scaledToFit()

抓取时间：2025-12-02T17:37:06Z

---

# scaledToFit()

**实例方法**

缩放此视图以适应其父视图。

## 声明

```swift
nonisolated func scaledToFit() -> some View

```

## 返回值

一个缩放此视图以适应其父视图的视图，并保持此视图的宽高比。

## 说明

使用 `scaledToFit()` 可缩放此视图以适应其父视图，并在缩放过程中保持视图的宽高比。

```swift
Circle()
    .fill(Color.pink)
    .scaledToFit()
    .frame(width: 300, height: 150)
    .border(Color(white: 0.75))
```

此方法等效于调用 [aspectRatio(_:contentMode:)](aspectRatio___contentMode.zh-Hans.md)，并指定 `nil` 宽高比和 [fit](../ContentMode/fit.zh-Hans.md) 内容模式。

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染得如同围绕指定轴在三维空间中旋转一样。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染得如同围绕指定轴在三维空间中旋转一样。

- **rotation3DEffect(_:anchor:)**：按指定的 3D 旋转值旋转视图内容。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的轴（以元素元组形式表示）旋转一定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/SwiftUI/View/scaledToFit()
crawled: 2025-12-02T17:37:06Z
---

# scaledToFit()

**Instance Method**

Scales this view to fit its parent.

## Declaration

```swift
nonisolated func scaledToFit() -> some View

```

## Return Value

A view that scales this view to fit its parent, maintaining this view’s aspect ratio.

## Discussion

Use `scaledToFit()` to scale this view to fit its parent, while maintaining the view’s aspect ratio as the view scales.

```swift
Circle()
    .fill(Color.pink)
    .scaledToFit()
    .frame(width: 300, height: 150)
    .border(Color(white: 0.75))
```



This method is equivalent to calling [aspectRatio(_:contentMode:)](aspectRatio___contentMode.zh-Hans.md) with a `nil` aspectRatio and a content mode of [fit](../ContentMode/fit.zh-Hans.md).

## Scaling, rotating, or transforming a view

- **scaledToFill()**: Scales this view to fill its parent.
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
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

