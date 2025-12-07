--- 来源：https://developer.apple.com/documentation/SwiftUI/RectangleCornerRadii
抓取时间：2025-12-02T17:36:43Z

---

# RectangleCornerRadii

**Structure**

描述具有不规则圆角的矩形的圆角半径值。

## 声明

```swift
@frozen struct RectangleCornerRadii
```

## 创建一组半径

- **init(topLeading:bottomLeading:bottomTrailing:topTrailing:)**：为具有不规则圆角的矩形创建一组新的圆角半径。

## 获取特定圆角的值

- **topLeading**：顶部前导圆角的半径。

- **topTrailing**：顶部后沿圆角的半径。

- **bottomLeading**：底部前导角的半径。

- **bottomTrailing**：底部后沿角的半径。

## 下标

- **subscript(_:)**：返回指定角的半径。

## 创建矩形

- **Rectangle**：位于视图框架内的矩形。

- **RoundedRectangle**：位于视图框架内的圆角矩形。

- **RoundedCornerStyle**：定义圆角矩形的角的形状。

- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md) 协议，用于描述圆角矩形。

- **RoundedRectangularShapeCorners**：描述 [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 的角样式的类型。

- **UnevenRoundedRectangle**：具有不同圆角值的矩形，与包含它的视图的框架对齐。

- **RectangleCornerInsets**：矩形角的内边距。

- **ConcentricRectangle**：被当前容器形状的同心版本替换的形状。如果容器形状是具有四个角的矩形派生形状，则此形状可以选择单独考虑每个角。

## 符合以下规范

- 可动画

- 可按位复制

- 可复制

- 可等值

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/RectangleCornerRadii
crawled: 2025-12-02T17:36:43Z
---

# RectangleCornerRadii

**Structure**

Describes the corner radius values of a rounded rectangle with uneven corners.

## Declaration

```swift
@frozen struct RectangleCornerRadii
```

## Creating a set of radii

- **init(topLeading:bottomLeading:bottomTrailing:topTrailing:)**: Creates a new set of corner radii for a rounded rectangle with uneven corners.

## Getting values for specific corners

- **topLeading**: The radius of the top-leading corner.
- **topTrailing**: The radius of the top-trailing corner.
- **bottomLeading**: The radius of the bottom-leading corner.
- **bottomTrailing**: The radius of the bottom-trailing corner.

## Subscripts

- **subscript(_:)**: Returns the corner radius for a certain corner.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

