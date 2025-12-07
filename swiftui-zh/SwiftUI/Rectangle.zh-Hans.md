---
来源： https://developer.apple.com/documentation/SwiftUI/Rectangle
抓取时间： 2025-12-02T16:22:30Z
---

# 矩形

**Structure**

在视图框架内对齐的矩形。

## 声明

```swift
@frozen struct Rectangle
```

## 创建一个矩形

- **init()**：创建新的矩形。

## 创建矩形

- **RoundedRectangle**：带圆角的矩形，在包含它的视图框架内对齐。
- **RoundedCornerStyle**：定义圆角矩形的边角形状。
- **RoundedRectangularShape**：[InsettableShape](InsettableShape.zh-Hans.md)的协议，描述圆角矩形的形状。
- **RoundedRectangularShapeCorners**：描述[RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 角样式的类型。
- **UnevenRoundedRectangle**：带有不同值的圆角矩形，在包含它的视图框架内对齐。
- **RectangleCornerRadii**：描述圆角矩形的边角半径值，边角不平整。
- **RectangleCornerInsets**：矩形边角的嵌入尺寸。
- **ConcentricRectangle**：由当前容器形状的同心版本替换的形状。如果容器形状是带有四个角的矩形派生形状，该形状可以选择单独尊重角。

## 符合

- 可动画
- 比特可复制
- 可复制
- 可嵌入形状
- 圆角矩形
- 可发送
- 可发送元数据类型
- 形状
- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/Rectangle
crawled: 2025-12-02T16:22:30Z
---

# Rectangle

**Structure**

A rectangular shape aligned inside the frame of the view containing it.

## Declaration

```swift
@frozen struct Rectangle
```

## Creating a rectangle

- **init()**: Creates a new rectangle shape.

## Creating rectangular shapes

- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- InsettableShape
- RoundedRectangularShape
- Sendable
- SendableMetatype
- Shape
- View

