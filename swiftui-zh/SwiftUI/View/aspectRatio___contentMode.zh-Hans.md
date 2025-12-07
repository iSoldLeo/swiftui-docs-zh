--- 来源：https://developer.apple.com/documentation/swiftui/view/aspectratio(_:contentmode:)

抓取时间：2025-12-03T06:27:30Z

---

# aspectRatio(_:contentMode:)

**实例方法**

将此视图的尺寸限制为指定的宽高比。

## 声明

```swift
nonisolated func aspectRatio(_ aspectRatio: CGFloat? = nil, contentMode: ContentMode) -> some View

```

## 参数

- **aspectRatio**：用于生成视图的宽高比。使用 `nil` 可在生成的视图中保持当前的宽高比。

- **contentMode**：一个标志，指示此视图是适应父上下文还是填充父上下文。

## 返回值

使用 `contentMode` 作为缩放算法，将此视图的尺寸限制为给定尺寸的宽高比。

## 说明

使用 `aspectRatio(_:contentMode:)` 可将视图的尺寸限制为 [doc://com.apple.documentation/documentation/CoreFoundation/CGFloat-swift.struct] 指定的宽高比，并使用指定的内容模式。

如果此视图可调整大小，则生成的视图将具有 `aspectRatio` 作为其宽高比。在本例中，紫色椭圆的宽高比为 3:4，并缩放以适应其框架：

```swift
Ellipse()
    .fill(Color.purple)
    .aspectRatio(0.75, contentMode: .fit)
    .frame(width: 200, height: 200)
    .border(Color(white: 0.75))
```

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的量在水平和垂直方向上缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直量缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **rotationEffect(_:anchor:)**：围绕指定点在二维方向上旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成绕指定轴旋转三维后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成绕指定轴旋转三维后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容旋转指定的三维旋转值。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的元素元组轴旋转一定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **ProjectionTransform**


---
source: https://developer.apple.com/documentation/swiftui/view/aspectratio(_:contentmode:)
crawled: 2025-12-03T06:27:30Z
---

# aspectRatio(_:contentMode:)

**Instance Method**

Constrains this view’s dimensions to the specified aspect ratio.

## Declaration

```swift
nonisolated func aspectRatio(_ aspectRatio: CGFloat? = nil, contentMode: ContentMode) -> some View

```

## Parameters

- **aspectRatio**: The ratio of width to height to use for the resulting view. Use `nil` to maintain the current aspect ratio in the resulting view.
- **contentMode**: A flag that indicates whether this view fits or fills the parent context.

## Return Value

A view that constrains this view’s dimensions to the aspect ratio of the given size using `contentMode` as its scaling algorithm.

## Discussion

Use `aspectRatio(_:contentMode:)` to constrain a view’s dimensions to an aspect ratio specified by a [doc://com.apple.documentation/documentation/CoreFoundation/CGFloat-swift.struct] using the specified content mode.

If this view is resizable, the resulting view will have `aspectRatio` as its aspect ratio. In this example, the purple ellipse has a 3:4 width-to-height ratio, and scales to fit its frame:

```swift
Ellipse()
    .fill(Color.purple)
    .aspectRatio(0.75, contentMode: .fit)
    .frame(width: 200, height: 200)
    .border(Color(white: 0.75))
```



## Scaling, rotating, or transforming a view

- **scaledToFill()**: Scales this view to fill its parent.
- **scaledToFit()**: Scales this view to fit its parent.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales this view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.
- **rotationEffect(_:anchor:)**: Rotates a view’s rendered output in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**

