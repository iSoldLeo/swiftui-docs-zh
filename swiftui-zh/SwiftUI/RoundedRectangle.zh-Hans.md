--- 来源：https://developer.apple.com/documentation/SwiftUI/RoundedRectangle
抓取时间：2025-12-02T17:27:45Z

---

# RoundedRectangle

**Structure**

一个圆角矩形，位于包含它的视图框架内。

## 声明

```swift
@frozen struct RoundedRectangle
```

## 创建圆角矩形

- **init(cornerRadius:style:)**：创建一个新的圆角矩形。

- **init(cornerSize:style:)**：创建一个新的圆角矩形。

## 获取形状特征

- **cornerSize**：圆角矩形的边长和高度。

- **style**：圆角矩形的边角样式。

## 支持类型

- **animatableData**：要进行动画处理的数据。

## 创建矩形

- **Rectangle**：位于包含它的视图框架内的矩形。

- **RoundedCornerStyle**：定义圆角矩形的边角形状。

- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md) 协议，用于描述圆角矩形。

- **RoundedRectangularShapeCorners**：描述 [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 边角样式的类型。

- **UnevenRoundedRectangle**：具有不同圆角值的矩形，位于包含它的视图框架内。

- **RectangleCornerRadii**：描述具有不规则圆角的矩形的圆角半径值。

- **RectangleCornerInsets**：矩形角的内嵌尺寸。

- **ConcentricRectangle**：被当前容器形状的同心版本替换的形状。如果容器形状是具有四个角的矩形派生形状，则此形状可以选择单独考虑每个角。

## 符合以下类型

- Animatable

- Copyable

- InsettableShape

- RoundedRectangularShape

- Sendable

- SendableMetatype

- Shape

- View


---
source: https://developer.apple.com/documentation/SwiftUI/RoundedRectangle
crawled: 2025-12-02T17:27:45Z
---

# RoundedRectangle

**Structure**

A rectangular shape with rounded corners, aligned inside the frame of the view containing it.

## Declaration

```swift
@frozen struct RoundedRectangle
```

## Creating a rounded rectangle

- **init(cornerRadius:style:)**: Creates a new rounded rectangle shape.
- **init(cornerSize:style:)**: Creates a new rounded rectangle shape.

## Getting the shape’s characteristics

- **cornerSize**: The width and height of the rounded rectangle’s corners.
- **style**: The style of corners drawn by the rounded rectangle.

## Supporting types

- **animatableData**: The data to animate.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Conforms To

- Animatable
- Copyable
- InsettableShape
- RoundedRectangularShape
- Sendable
- SendableMetatype
- Shape
- View

