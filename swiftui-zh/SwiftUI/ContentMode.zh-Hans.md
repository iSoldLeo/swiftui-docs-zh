--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentMode

抓取时间：2025-12-02T17:37:21Z

---

# ContentMode

**Enumeration**

定义视图内容如何填充可用空间的常量。

## 声明

```swift
@frozen enum ContentMode
```

## 获取内容模式

- **ContentMode.fill**：此选项会调整内容大小，使其占据所有可用空间（包括垂直和水平方向）。

- **ContentMode.fit**：此选项会调整内容大小，使其位于可用空间内（包括垂直和水平方向）。

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：将视图内容旋转指定的三维旋转角度。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的元素元组轴旋转指定角度。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对当前视图的渲染输出应用 3D 变换。

- **projectionEffect(_:)**：对当前视图的渲染输出应用投影变换。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可大小写迭代 (CaseIterable)

- 可复制 (Copyable)

- 可等值 (Equatable)

- 可哈希 (Hashable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/SwiftUI/ContentMode
crawled: 2025-12-02T17:37:21Z
---

# ContentMode

**Enumeration**

Constants that define how a view’s content fills the available space.

## Declaration

```swift
@frozen enum ContentMode
```

## Getting content modes

- **ContentMode.fill**: An option that resizes the content so it occupies all available space, both vertically and horizontally.
- **ContentMode.fit**: An option that resizes the content so it’s all within the available space, both vertically and horizontally.

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
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

