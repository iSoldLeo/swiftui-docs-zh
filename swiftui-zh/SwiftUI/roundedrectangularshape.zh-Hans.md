--- 来源：https://developer.apple.com/documentation/swiftui/roundedrectangularshape

抓取时间：2025-12-04T11:33:38Z

---

# RoundedRectangularShape

**Protocol**

[InsettableShape](InsettableShape.zh-Hans.md) 协议，用于描述圆角矩形。

## 声明

```swift
protocol RoundedRectangularShape : InsettableShape
```

## 概述

当您的形状是具有四个角的圆角矩形，并且您希望公开有关角的信息时，请将您的 [InsettableShape](InsettableShape.zh-Hans.md) 类型符合 [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 协议。例如，自定义三角形 [Shape](Shape.zh-Hans.md) 不适合这种一致性，而自定义矩形 [Shape](Shape.zh-Hans.md) 则可以从提供此实现中受益，尤其是在该形状用作 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/containerShape(_:)-3br47] 中的容器形状以实现同心度时。

系统形状如 [Rectangle](Rectangle.zh-Hans.md)、[RoundedRectangle](RoundedRectangle.zh-Hans.md)、[UnevenRoundedRectangle](UnevenRoundedRectangle.zh-Hans.md)、[Capsule](Capsule.zh-Hans.md) 和 [Circle](Circle.zh-Hans.md) 已为此协议提供了默认实现。

## 实例方法

- **corners(in:)**：根据尺寸解析角点。如果形状的角点样式与尺寸相关，则读取提供的尺寸并相应地返回值。当尺寸尚未确定时，可以调用此函数并传入 nil 值。在这种情况下，返回最佳近似值。例如，对于胶囊形状，其圆角半径由尺寸决定。如果尺寸不可用，则返回 `.fixed(.infinity)` 以指示圆角应尽可能圆润。

## 类型别名

- **RoundedRectangularShape.Corners**

## 创建矩形形状

- **Rectangle**：位于包含它的视图框架内的矩形形状。

- **RoundedRectangle**：位于包含它的视图框架内的圆角矩形形状。

- **RoundedCornerStyle**：定义圆角矩形的角形状。

- **RoundedRectangularShapeCorners**：描述 [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) 的角样式的类型。

- **UnevenRoundedRectangle**：具有不同圆角值的矩形，位于包含它的视图框架内。

- **RectangleCornerRadii**：描述具有不规则圆角的矩形的圆角半径值。

- **RectangleCornerInsets**：矩形的内角尺寸。

- **ConcentricRectangle**：一种形状，会被当前容器形状的同心版本替换。如果容器形状是具有四个角的矩形派生形状，则此形状可以选择单独考虑每个角。

## 继承自

- Animatable

- InsettableShape

- Sendable

- SendableMetatype

- Shape

- View

## 符合的类型

- Capsule

- Circle

- Rectangle
- RoundedRectangle
- UnevenRoundedRectangle


---
source: https://developer.apple.com/documentation/swiftui/roundedrectangularshape
crawled: 2025-12-04T11:33:38Z
---

# RoundedRectangularShape

**Protocol**

A protocol of [InsettableShape](InsettableShape.zh-Hans.md) that describes a rounded rectangular shape.

## Declaration

```swift
protocol RoundedRectangularShape : InsettableShape
```

## Overview

Conform your [InsettableShape](InsettableShape.zh-Hans.md) type to [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md) when your shape is a rounded rectangular with four corners and you want to expose information about the corners. For example, a custom triangle [Shape](Shape.zh-Hans.md) is not fit for such conformance, while a custom rectangle [Shape](Shape.zh-Hans.md) could benefit from providing the implementation, especially when the shape is used as a container shape in [doc://com.apple.SwiftUI/documentation/SwiftUI/View/containerShape(_:)-3br47] to achieve concentricity.

System shapes like [Rectangle](Rectangle.zh-Hans.md), [RoundedRectangle](RoundedRectangle.zh-Hans.md), [UnevenRoundedRectangle](UnevenRoundedRectangle.zh-Hans.md), [Capsule](Capsule.zh-Hans.md), and [Circle](Circle.zh-Hans.md) already provide default implementation for this protocol.

## Instance Methods

- **corners(in:)**: Resolved corners given a size. If the corner style of a shape is size-dependent, read the provided size and return values accordingly. This function could be called with a nil size when the size hasn’t been determined. In that case, return the best approximated value. For example, for a capsule shape, its corner radius is determined by the size. If size is not available, return `.fixed(.infinity)` to indicate that the corner should be as round as it could be.

## Type Aliases

- **RoundedRectangularShape.Corners**

## Creating rectangular shapes

- **Rectangle**: A rectangular shape aligned inside the frame of the view containing it.
- **RoundedRectangle**: A rectangular shape with rounded corners, aligned inside the frame of the view containing it.
- **RoundedCornerStyle**: Defines the shape of a rounded rectangle’s corners.
- **RoundedRectangularShapeCorners**: A type describing the corner styles of a [RoundedRectangularShape](RoundedRectangularShape.zh-Hans.md).
- **UnevenRoundedRectangle**: A rectangular shape with rounded corners with different values, aligned inside the frame of the view containing it.
- **RectangleCornerRadii**: Describes the corner radius values of a rounded rectangle with uneven corners.
- **RectangleCornerInsets**: The inset sizes for the corners of a rectangle.
- **ConcentricRectangle**: A shape that is replaced by a concentric version of the current container shape. If the container shape is a rectangle derived shape with four corners, this shape could choose to respect corners individually.

## Inherits From

- Animatable
- InsettableShape
- Sendable
- SendableMetatype
- Shape
- View

## Conforming Types

- Capsule
- Circle
- Rectangle
- RoundedRectangle
- UnevenRoundedRectangle

