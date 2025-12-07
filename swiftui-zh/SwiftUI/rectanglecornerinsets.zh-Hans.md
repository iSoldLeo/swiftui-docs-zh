--- 来源：https://developer.apple.com/documentation/swiftui/rectanglecornerinsets
抓取时间：2025-12-04T13:24:24Z

---

# RectangleCornerInsets

**Structure**

矩形角点的内边距。

## 声明

```swift
@frozen struct RectangleCornerInsets
```

## 初始化

- **init()**

- **init(topLeading:topTrailing:bottomLeading:bottomTrailing:)**

## 实例属性

- **bottomLeading**：底部前导角的内边距。

- **bottomTrailing**：底部后导角的内边距。

- **topLeading**：顶部前导角内切线的大小。

- **topTrailing**：顶部后导角内切线的大小。

## 创建矩形

- **Rectangle**：位于包含它的视图框架内的矩形。

- **RoundedRectangle**：位于包含它的视图框架内的圆角矩形。

- **RoundedCornerStyle**：定义圆角矩形的角形状。

- **RoundedRectangularShape**：描述圆角矩形的 [InsettableShape](InsettableShape.zh-Hans.md) 协议。

- **RoundedRectangularShapeCorners**：描述 [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 的角样式的类型。

- **UnevenRoundedRectangle**：一个具有不同圆角值的矩形，位于包含它的视图框架内。

- **RectangleCornerRadii**：描述一个圆角矩形的圆角半径值（圆角半径不均匀）。

- **ConcentricRectangle**：一个会被当前容器形状的同心版本替换的形状。如果容器形状是一个具有四个角的矩形派生形状，则此形状可以选择单独考虑每个角。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 可等值 (Equatable)

- 可哈希 (Hashable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/swiftui/rectanglecornerinsets
crawled: 2025-12-04T13:24:24Z
---

# RectangleCornerInsets

**Structure**

The inset sizes for the corners of a rectangle.

## Declaration

```swift
@frozen struct RectangleCornerInsets
```

## Initializers

- **init()**
- **init(topLeading:topTrailing:bottomLeading:bottomTrailing:)**

## Instance Properties

- **bottomLeading**: The size of the bottom-leading corner inset.
- **bottomTrailing**: The size of the bottom-trailing corner inset.
- **topLeading**: The size of the top-leading corner inset.
- **topTrailing**: The size of the top-trailing corner inset.

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShape**: A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

