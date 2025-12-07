--- 来源：https://developer.apple.com/documentation/swiftui/view/scaleeffect(_:anchor:)

抓取时间：2025-12-01T11:16:36Z

---

# scaleEffect(_:anchor:)

**实例方法**

根据给定的锚点，按指定比例缩放此视图的渲染输出，水平和垂直方向均如此。

## 声明

```swift
nonisolated func scaleEffect(_ s: CGFloat, anchor: UnitPoint = .center) -> ModifiedContent<Self, _UniformScaleEffect>
```

## 参数

- **s**：视图在水平和垂直方向上的缩放比例。

- **anchor**：锚点，默认值为 [center](../UnitPoint/center.zh-Hans.md)，指示缩放操作的起始位置。

## 讨论

使用 `scaleEffect(_:anchor:)` 对视图应用水平和垂直缩放变换。

```swift
Image(systemName: "envelope.badge.fill")
    .resizable()
    .frame(width: 100, height: 100, alignment: .center)
    .foregroundColor(Color.red)
    .scaleEffect(2, anchor: .leading)
    .border(Color.gray)
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸约束为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容旋转指定的三维旋转角度。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的元素元组轴旋转指定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**

- **ContentMode**：定义视图内容如何填充可用空间的常量。


---
source: https://developer.apple.com/documentation/swiftui/view/scaleeffect(_:anchor:)
crawled: 2025-12-01T11:16:36Z
---

# scaleEffect(_:anchor:)

**Instance Method**

Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.

## Declaration

```swift
nonisolated func scaleEffect(_ s: CGFloat, anchor: UnitPoint = .center) -> ModifiedContent<Self, _UniformScaleEffect>
```

## Parameters

- **s**: The amount to scale the view in the view in both the horizontal and vertical directions.
- **anchor**: The anchor point with a default of [center](../UnitPoint/center.zh-Hans.md) that indicates the starting position for the scale operation.

## Discussion

Use `scaleEffect(_:anchor:)` to apply a horizontally and vertically scaling transform to a view.

```swift
Image(systemName: "envelope.badge.fill")
    .resizable()
    .frame(width: 100, height: 100, alignment: .center)
    .foregroundColor(Color.red)
    .scaleEffect(2, anchor: .leading)
    .border(Color.gray)
```



## Scaling, rotating, or transforming a view

- **scaledToFill()**: Scales this view to fill its parent.
- **scaledToFit()**: Scales this view to fit its parent.
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
- **ContentMode**: Constants that define how a view’s content fills the available space.

