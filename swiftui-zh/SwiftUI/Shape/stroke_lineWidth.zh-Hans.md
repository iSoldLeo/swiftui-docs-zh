---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/stroke(lineWidth:)
抓取时间： 2025-12-02T21:41:54Z
---

# stroke(lineWidth:)

**实例方法**

返回一个新形状，它是`self` 的描边副本，线宽由 `lineWidth` 定义，`StrokeStyle` 的所有其他属性均为默认值。

### 声明

```swift
nonisolated func stroke(lineWidth: CGFloat = 1) -> some Shape

```

## 设置冲程特性

- **stroke(_:lineWidth:)**：用颜色或渐变描边该形状的轮廓。
- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变描画此形状的轮廓。
- **stroke(_:style:)**：用颜色或渐变描画此形状的轮廓。
- **stroke(_:style:antialiased:)**：用颜色或渐变描画此形状的轮廓。
- **stroke(style:)**：使用`style` 的内容定义描边特征，返回一个新形状，它是`self` 的描边副本。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/stroke(lineWidth:)
crawled: 2025-12-02T21:41:54Z
---

# stroke(lineWidth:)

**Instance Method**

Returns a new shape that is a stroked copy of `self` with line-width defined by `lineWidth` and all other properties of `StrokeStyle` having their default values.

## Declaration

```swift
nonisolated func stroke(lineWidth: CGFloat = 1) -> some Shape

```

## Setting the stroke characteristics

- **stroke(_:lineWidth:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:style:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(style:)**: Returns a new shape that is a stroked copy of `self`, using the contents of `style` to define the stroke characteristics.

