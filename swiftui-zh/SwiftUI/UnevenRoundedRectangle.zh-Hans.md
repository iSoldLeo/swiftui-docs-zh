---
来源： https://developer.apple.com/documentation/SwiftUI/UnevenRoundedRectangle
抓取时间：2025-12-02T17:28:00Z
---

# UnevenRoundedRectangle

**Structure**

带有不同圆角值的矩形，在包含该矩形的视图框架内对齐。

## 声明

```swift
@frozen struct UnevenRoundedRectangle
```

## 创建不平整的圆角矩形

- **init(cornerRadii:style:)**：创建一个四角不平整的新圆角矩形。
- **init(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**：创建新的圆角不平整的矩形。

## 获取形状的特征

- **cornerRadii**：圆角矩形每个角的半径。
- **style**：圆角矩形绘制的角的样式。

## 支持类型

- **animatableData**：要制作成动画的数据。

## 创建矩形形状

- **Rectangle**：在视图框架内对齐的矩形。
- **RoundedRectangle**：带圆角的矩形，在包含它的视图的边框内对齐。
- **RoundedCornerStyle**：定义圆角矩形的边角形状。
- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md)的协议，描述圆角矩形的形状。
- **RoundedRectangularShapeCorners**：描述[RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 角样式的类型。
- **RectangleCornerRadii**：描述四角不平的圆角矩形的圆角半径值。
- **RectangleCornerInsets**：矩形边角的嵌入尺寸。
- **ConcentricRectangle**：由当前容器形状的同心版本替换的形状。如果容器形状是带有四个角的矩形派生形状，该形状可以选择单独尊重角。

## 符合

- 可动画
- 可复制
- 可嵌入形状
- 圆角矩形
- 可发送
- 可发送元类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/UnevenRoundedRectangle
crawled: 2025-12-02T17:28:00Z
---

# UnevenRoundedRectangle

**Structure**

A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.

## Declaration

```swift
@frozen struct UnevenRoundedRectangle
```

## Creating an uneven rounded rectangle

- **init(cornerRadii:style:)**: Creates a new rounded rectangle shape with uneven corners.
- **init(topLeadingRadius:bottomLeadingRadius:bottomTrailingRadius:topTrailingRadius:style:)**: Creates a new rounded rectangle shape with uneven corners.

## Getting the shape’s characteristics

- **cornerRadii**: The radii of each corner of the rounded rectangle.
- **style**: The style of corners drawn by the rounded rectangle.

## Supporting types

- **animatableData**: The data to animate.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
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

