--- 来源：https://developer.apple.com/documentation/SwiftUI/InsettableShape
抓取时间：2025-12-02T17:26:31Z

---

# InsettableShape

**Protocol**

一种能够内嵌自身以生成其他形状的形状类型。

## 声明

```swift
protocol InsettableShape : Shape
```

## 设置描边边框特征

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是将 `self` 的 `lineWidth` 大小的边框（也称为内描边）填充为 `content` 的结果。这相当于将 `self` 内缩 `lineWidth / 2`，并使用 `lineWidth` 作为线宽描边。

- **strokeBorder(lineWidth:antialiased:)**：返回一个视图，该视图是将 `self` 的 `lineWidth` 大小的边框（也称为内描边）填充为前景色的结果。这相当于将 `self` 内缩 `lineWidth / 2`，并使用 `lineWidth` 作为线宽描边。

- **strokeBorder(_:style:antialiased:)**：返回一个视图，该视图是通过将 `self` 内移 `style.lineWidth / 2`，然后用 `style` 描边，最后填充 `content` 而得到的。

- **strokeBorder(style:antialiased:)**：返回一个视图，该视图是通过将 `self` 内移 `style.lineWidth / 2`，然后用 `style` 描边，最后填充前景色而得到的。

## 设置内移量

- **inset(by:)**：返回内移 `self` `amount` 的结果。

- **InsetShape**：内嵌形状的类型。

## 设置容器形状

- **containerShape(_:)**：设置此视图中任何容器相对形状或同心矩形所使用的容器形状。

- **ContainerRelativeShape**：将被当前容器形状的内嵌版本替换的形状。如果未定义容器形状，则替换为矩形。

## 继承自

- Animatable

- Sendable

- SendableMetatype

- Shape

- View

## 被继承自

- RoundedRectangularShape

## 符合的类型

- ButtonBorderShape

- Capsule

- Circle

- ContainerRelativeShape

- Ellipse

- OffsetShape

- Rectangle

- RotatedShape

- RoundedRectangle

- UnevenRoundedRectangle


---
source: https://developer.apple.com/documentation/SwiftUI/InsettableShape
crawled: 2025-12-02T17:26:31Z
---

# InsettableShape

**Protocol**

A shape type that is able to inset itself to produce another shape.

## Declaration

```swift
protocol InsettableShape : Shape
```

## Setting the stroke border characteristics

- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that is the result of filling the `lineWidth`-sized border (aka inner stroke) of `self` with `content`. This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.
- **strokeBorder(lineWidth:antialiased:)**: Returns a view that is the result of filling the `lineWidth`-sized border (aka inner stroke) of `self` with the foreground color. This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.
- **strokeBorder(_:style:antialiased:)**: Returns a view that is the result of insetting `self` by `style.lineWidth / 2`, stroking the resulting shape with `style`, and then filling with `content`.
- **strokeBorder(style:antialiased:)**: Returns a view that is the result of insetting `self` by `style.lineWidth / 2`, stroking the resulting shape with `style`, and then filling with the foreground color.

## Setting the inset

- **inset(by:)**: Returns `self` inset by `amount`.
- **InsetShape**: The type of the inset shape.

## Setting a container shape

- **containerShape(_:)**: Sets the container shape to use for any container relative shape or concentric rectangle within this view.
- **ContainerRelativeShape**: A shape that is replaced by an inset version of the current container shape. If no container shape was defined, is replaced by a rectangle.

## Inherits From

- Animatable
- Sendable
- SendableMetatype
- Shape
- View

## Inherited By

- RoundedRectangularShape

## Conforming Types

- ButtonBorderShape
- Capsule
- Circle
- ContainerRelativeShape
- Ellipse
- OffsetShape
- Rectangle
- RotatedShape
- RoundedRectangle
- UnevenRoundedRectangle

