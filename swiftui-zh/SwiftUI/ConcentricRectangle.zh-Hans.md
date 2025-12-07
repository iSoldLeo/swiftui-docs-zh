---
来源： https://developer.apple.com/documentation/SwiftUI/ConcentricRectangle
抓取时间： 2025-12-02T17:26:43Z
---

# 同心矩形

**Structure**

用当前容器形状的同心版本替换的形状。如果容器形状是带有四个角的矩形派生形状，该形状可以选择单独尊重角。

## 声明

```swift
struct ConcentricRectangle
```

## 概览

要使用[ConcentricRectangle](ConcentricRectangle.zh-Hans.md)，首先要确保祖先视图层次结构提供了容器形状。有些容器形状是由平台套件提供的，但你也可以通过编写带有形状的[doc://com.apple.SwiftUI/documentation/SwiftUI/View/containerShape(_:)-3br47]修饰符来提供自己的容器形状。然后，调用[ConcentricRectangle](ConcentricRectangle.zh-Hans.md) 的初始化器之一或使用静态[Shape](Shape.zh-Hans.md) 方便创建同心圆形状。

```swift
    ZStack {
        Color.cyan
            .fill(.rect(corners: .concentric(minimum: 12), isUniform: false))
            .padding(.all, padding)
    }
    .containerShape(.rect(cornerRadius: 24))
```

上面的示例将生成一个四边都被`padding` 嵌入的形状。它将与其容器形状保持同心，而容器形状的边角半径为 24 pts，因此该形状的半径较小，填充较多。不过，由于我们提供了一个最小值，因此半径将至少为 12 pts，以确保形状不会出现方角。

[ConcentricRectangle](ConcentricRectangle.zh-Hans.md)还通过初始化程序为每个角提供不同的样式，从而实现对每个角的控制。

```swift
ConcentricRectangle(
    topLeadingCorner: 0,
    topTrailingCorner: 28,
    bottomLeadingCorner: .concentric,
    bottomTrailingCorner: .concentric(minimum: 12)
)
```

上例中，上前角为正方形，上后角为半径为 28 pts 的常数，下前角为与容器形状同心的角，下后角为具有最小半径的同心角。

如果您希望[ConcentricRectangle](ConcentricRectangle.zh-Hans.md) 在两个角上对称，请使用初始化程序创建形状，为矩形上的任意两个角设置统一的角样式。[ConcentricRectangle](ConcentricRectangle.zh-Hans.md)仍将单独解决角半径问题，但会使用角的最大值作为统一角的最终共享角半径。

如果提供的容器形状不是[RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 兼容的形状，[ConcentricRectangle](ConcentricRectangle.zh-Hans.md) 将无法根据同心度来解决边角半径问题。在这种情况下，它将退回到[ContainerRelativeShape](ContainerRelativeShape.zh-Hans.md)，即容器形状的嵌入版本。





## 初始化器

- **init()**：创建一个同心矩形，每个角都与容器形状同心。
- **init(corners:isUniform:)**：创建一个矩形，在四个角上设置相同的角样式。
- **init(topLeadingCorner:topTrailingCorner:bottomLeadingCorner:bottomTrailingCorner:)**：创建具有四个角的单独样式的矩形。
- **init(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)**：创建一个矩形，上面两个角统一设置一种角样式，下面两个角分别设置另外两种样式。
- **init(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)**：创建一个矩形，在前两个角上统一设置一种角样式，在后两个角上分别设置另外两种样式。
- **init(uniformLeadingCorners:uniformTrailingCorners:)**：创建一个矩形，在前面的两个角上统一设置一种角样式，在后面的两个角上统一设置另一种样式。
- **init(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)**：创建一个矩形，在上面两个角上统一设置一种角样式，在下面两个角上分别设置另外两种样式。
- **init(uniformTopCorners:uniformBottomCorners:)**：创建一个矩形，在上面两个角上统一设置一个角样式，在下面两个角上统一设置另一个角样式。
- **init(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)**：创建一个矩形，在尾部的两个角上统一设置一种角样式，在前部的两个角上分别设置另外两种样式。

## 创建矩形

- **Rectangle**：在视图框架内对齐的矩形。
- **RoundedRectangle**：带圆角的矩形，在包含它的视图的边框内对齐。
- **RoundedCornerStyle**：定义圆角矩形的边角形状。
- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md)的协议，描述圆角矩形的形状。
- **RoundedRectangularShapeCorners**：描述[RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 角样式的类型。
- **UnevenRoundedRectangle**：带有不同值的圆角矩形，在包含它的视图框架内对齐。
- **RectangleCornerRadii**：描述圆角矩形的边角半径值，边角不平整。
- **RectangleCornerInsets**：矩形四角的嵌入尺寸。

## 符合

- 可动画
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/ConcentricRectangle
crawled: 2025-12-02T17:26:43Z
---

# ConcentricRectangle

**Structure**

A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Declaration

```swift
struct ConcentricRectangle
```

## Overview

To use [ConcentricRectangle](ConcentricRectangle.zh-Hans.md), first make sure the ancestor view hierarchy provides the container shape. Some container shapes are provided by platform kits, but you could provide your own by writing the [doc://com.apple.SwiftUI/documentation/SwiftUI/View/containerShape(_:)-3br47] modifier with a shape. Then, either call one of the initializers of [ConcentricRectangle](ConcentricRectangle.zh-Hans.md) or use the static [Shape](Shape.zh-Hans.md) convenience to create the concentric shape.

```swift
    ZStack {
        Color.cyan
            .fill(.rect(corners: .concentric(minimum: 12), isUniform: false))
            .padding(.all, padding)
    }
    .containerShape(.rect(cornerRadius: 24))
```

The above example will generate a shape that is inset by `padding` on all sides. It will stay concentric to its container shape which has a 24 pts corner radius, so the shape will have a smaller radius with more padding. However, since here we provided a minimum value, the radius will be at least 12 pts, ensuring the shape to never have a square corner.

[ConcentricRectangle](ConcentricRectangle.zh-Hans.md) also provides per-corner control with the initializers that take different styles for each corner.

```swift
ConcentricRectangle(
    topLeadingCorner: 0,
    topTrailingCorner: 28,
    bottomLeadingCorner: .concentric,
    bottomTrailingCorner: .concentric(minimum: 12)
)
```

The above example will have the top leading corner as square, the top trailing corner as constant 28 pts radius, the bottom leading as concentric to container shape, and bottom trailing as concentric with a minimum radius.

If you wish [ConcentricRectangle](ConcentricRectangle.zh-Hans.md) to be symmetric on two corners, create the shape with initializers that takes an uniform corner style for any two corners on the rectangle. [ConcentricRectangle](ConcentricRectangle.zh-Hans.md) will still resolves corner radius individually, but use the maximum value out of the corners as the final, shared corner radius of the uniform corners.

When the container shape provided is not a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) compatible shape, [ConcentricRectangle](ConcentricRectangle.zh-Hans.md) will not be able to resolve corner radius based on concentricity. In those cases, it will fallback to be a [ContainerRelativeShape](ContainerRelativeShape.zh-Hans.md), which is an inset version of the container shape.





## Initializers

- **init()**: Create a concentric rectangle with each corner being concentric individually to the container shape.
- **init(corners:isUniform:)**: Create a rectangle with the same corner style set on four corners.
- **init(topLeadingCorner:topTrailingCorner:bottomLeadingCorner:bottomTrailingCorner:)**: Create a rectangle with individual styles of four corners.
- **init(uniformBottomCorners:topLeadingCorner:topTrailingCorner:)**: Create a rectangle with a corner style set on the top two corners uniformly, and two other styles for the bottom two corners respectively.
- **init(uniformLeadingCorners:topTrailingCorner:bottomTrailingCorner:)**: Create a rectangle with a corner style set on the leading two corners uniformly, and two other styles for the trailing two corners respectively.
- **init(uniformLeadingCorners:uniformTrailingCorners:)**: Create a rectangle with a corner style set on the leading two corners uniformly, and another style set on the trailing two corners uniformly.
- **init(uniformTopCorners:bottomLeadingCorner:bottomTrailingCorner:)**: Create a rectangle with a corner style set on the top two corners uniformly, and two other styles for the bottom two corners respectively.
- **init(uniformTopCorners:uniformBottomCorners:)**: Create a rectangle with a corner style set on the top two corners uniformly, and another style set on the bottom two corners uniformly.
- **init(uniformTrailingCorners:topLeadingCorner:bottomLeadingCorner:)**: Create a rectangle with a corner style set on the trailing two corners uniformly, and two other styles for the leading two corners respectively.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.

## Conforms To

- Animatable
- Sendable
- SendableMetatype
- Shape
- View

