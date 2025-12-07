---
来源： https://developer.apple.com/documentation/swiftui/roundedcornerstyle
抓取时间： 2025-12-04T11:33:49Z
---

# 圆角风格

**Enumeration**

定义圆角矩形的边角形状。

## 声明

```swift
enum RoundedCornerStyle
```

## 获取边角样式

- **RoundedCornerStyle.circular**：四分之一圆角矩形。
- **RoundedCornerStyle.continuous**：连续曲率圆角。

## 创建矩形

- **Rectangle**：在视图框架内对齐的矩形。
- **RoundedRectangle**：带圆角的矩形，在包含它的视图的边框内对齐。
- **RoundedRectangularShape**：描述圆角矩形的[InsettableShape](InsettableShape.zh-Hans.md) 协议。
- **RoundedRectangularShapeCorners**：描述[RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 角样式的类型。
- **UnevenRoundedRectangle**：带有不同值的圆角矩形，在包含它的视图框架内对齐。
- **RectangleCornerRadii**：描述圆角矩形的边角半径值，边角不平整。
- **RectangleCornerInsets**：矩形边角的嵌入尺寸。
- **ConcentricRectangle**：由当前容器形状的同心版本替换的形状。如果容器形状是带有四个角的矩形派生形状，该形状可以选择单独尊重角。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/roundedcornerstyle
crawled: 2025-12-04T11:33:49Z
---

# RoundedCornerStyle

**Enumeration**

Defines the shape of a rounded rectangle’s corners.

## Declaration

```swift
enum RoundedCornerStyle
```

## Getting corner styles

- **RoundedCornerStyle.circular**: Quarter-circle rounded rect corners.
- **RoundedCornerStyle.continuous**: Continuous curvature rounded rect corners.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

