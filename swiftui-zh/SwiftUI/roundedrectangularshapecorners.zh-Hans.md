--- 来源：https://developer.apple.com/documentation/swiftui/roundedrectangularshapecorners
抓取时间：2025-12-04T11:33:38Z

---

# RoundedRectangularShapeCorners

**Structure**

描述 [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 的圆角样式的类型。

## 声明

```swift
struct RoundedRectangularShapeCorners
```

## 初始化器

- **init(all:)**：创建所有圆角样式相同的圆角样式。

- **init(topLeading:topTrailing:bottomLeading:bottomTrailing:)**：创建每个圆角样式不同的圆角样式。

## 实例属性

- **bottomLeading**：底部前导角样式。

- **bottomTrailing**：底部尾角样式

- **topLeading**：顶部前角样式

- **topTrailing**：顶部尾角样式

## 下标

- **subscript(_:)**：返回指定角的样式。

## 类型属性

- **concentric**：角样式与其容器同心，四个角的半径根据需要进行调整。

## 类型方法

- **concentric(minimum:)**：角样式与其容器同心，四个角的半径根据需要进行调整，但半径永远不会小于零，或者小于提供的最小角样式值（如果已提供）。

- **fixed(_:)**：四个角的半径固定。

## 创建矩形

- **Rectangle**：位于视图框架内的矩形。

- **RoundedRectangle**：位于视图框架内的圆角矩形。

- **RoundedCornerStyle**：定义圆角矩形的角形状。

- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md) 协议，用于描述圆角矩形。

- **UnevenRoundedRectangle**：位于视图框架内的圆角矩形，圆角半径值各不相同。

- **RectangleCornerRadii**：描述圆角矩形的角半径值。

- **RectangleCornerInsets**：矩形角的内边距。 - **ConcentricRectangle**：一种形状，它会被当前容器形状的同心版本所替换。如果容器形状是由四个角组成的矩形派生形状，则此形状可以选择单独考虑每个角。

## 符合以下标准

- 可动画化

- 可等值化

- 可哈希化

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/roundedrectangularshapecorners
crawled: 2025-12-04T11:33:38Z
---

# RoundedRectangularShapeCorners

**Structure**

A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).

## Declaration

```swift
struct RoundedRectangularShapeCorners
```

## Initializers

- **init(all:)**: Create corner styles with all corner having the same style.
- **init(topLeading:topTrailing:bottomLeading:bottomTrailing:)**: Create corner styles with per-corner styles.

## Instance Properties

- **bottomLeading**: The bottom leading corner style.
- **bottomTrailing**: The bottom trailing corner style
- **topLeading**: The top leading corner style.
- **topTrailing**: The top trailing corner style.

## Subscripts

- **subscript(_:)**: Returns the corner style for a provided corner.

## Type Properties

- **concentric**: Corner styles will be concentric with its container, varying the radius as needed in all four corners.

## Type Methods

- **concentric(minimum:)**: Corner styles will be concentric with its container, varying the radius as needed in all four corners but never going below zero, or the provided minimum corner style, if provided.
- **fixed(_:)**: Corner styles with fixed radius in all four corners.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Conforms To

- Animatable
- Equatable
- Hashable
- Sendable
- SendableMetatype

