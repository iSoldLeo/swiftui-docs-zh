---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/stroke(style:)
抓取时间： 2025-12-01T02:32:54Z
---

# stroke(style:)

**实例方法**

返回一个新形状，它是`self` 的描边副本，使用`style` 的内容定义描边特征。

## 声明

```swift
nonisolated func stroke(style: StrokeStyle) -> some Shape

```

## 设置冲程特性

- **stroke(_:lineWidth:)**：用颜色或渐变描边该形状的轮廓。
- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变描画此形状的轮廓。
- **stroke(lineWidth:)**：返回一个新形状，它是`self` 的描边副本，线宽由 `lineWidth` 定义，`StrokeStyle` 的所有其他属性均为默认值。
- **stroke(_:style:)**：用颜色或梯度描边该形状的轮廓。
- **stroke(_:style:antialiased:)**：用颜色或渐变描画此形状的轮廓。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/stroke(style:)
crawled: 2025-12-01T02:32:54Z
---

# stroke(style:)

**Instance Method**

Returns a new shape that is a stroked copy of `self`, using the contents of `style` to define the stroke characteristics.

## Declaration

```swift
nonisolated func stroke(style: StrokeStyle) -> some Shape

```

## Setting the stroke characteristics

- **stroke(_:lineWidth:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(lineWidth:)**: Returns a new shape that is a stroked copy of `self` with line-width defined by `lineWidth` and all other properties of `StrokeStyle` having their default values.
- **stroke(_:style:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.

