---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/stroke(_:style:)
抓取时间： 2025-12-02T21:41:55Z
---

# stroke(_:style:)

**实例方法**

使用颜色或梯度描边此形状的轮廓。

## 声明

```swift
nonisolated func stroke<S>(_ content: S, style: StrokeStyle) -> some View where S : ShapeStyle

```

## 参数

- **content**：用于描边此形状的颜色或渐变色。
- **style**：描边特性，如线条的宽度和描边是否为虚线，决定如何呈现此形状。

## 返回值

描边后的形状。

## 讨论

下面的示例为`Capsule`添加了紫色虚线描边：

```swift
Capsule()
.stroke(
    Color.purple,
    style: StrokeStyle(
        lineWidth: 5,
        lineCap: .round,
        lineJoin: .miter,
        miterLimit: 0,
        dash: [5, 10],
        dashPhase: 0
    )
)
```

## 设置笔划特征

- **stroke(_:lineWidth:)**：用颜色或渐变描边该形状的轮廓。
- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变描画此形状的轮廓。
- **stroke(lineWidth:)**：返回一个新形状，它是`self` 的描边副本，线宽由 `lineWidth` 定义，`StrokeStyle` 的所有其他属性均为默认值。
- **stroke(_:style:antialiased:)**：用颜色或梯度描边该形状的轮廓。
- **stroke(style:)**：使用`style` 的内容定义描边特征，返回一个新形状，它是`self` 的描边副本。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/stroke(_:style:)
crawled: 2025-12-02T21:41:55Z
---

# stroke(_:style:)

**Instance Method**

Traces the outline of this shape with a color or gradient.

## Declaration

```swift
nonisolated func stroke<S>(_ content: S, style: StrokeStyle) -> some View where S : ShapeStyle

```

## Parameters

- **content**: The color or gradient with which to stroke this shape.
- **style**: The stroke characteristics — such as the line’s width and whether the stroke is dashed — that determine how to render this shape.

## Return Value

A stroked shape.

## Discussion

The following example adds a dashed purple stroke to a `Capsule`:

```swift
Capsule()
.stroke(
    Color.purple,
    style: StrokeStyle(
        lineWidth: 5,
        lineCap: .round,
        lineJoin: .miter,
        miterLimit: 0,
        dash: [5, 10],
        dashPhase: 0
    )
)
```

## Setting the stroke characteristics

- **stroke(_:lineWidth:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(lineWidth:)**: Returns a new shape that is a stroked copy of `self` with line-width defined by `lineWidth` and all other properties of `StrokeStyle` having their default values.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(style:)**: Returns a new shape that is a stroked copy of `self`, using the contents of `style` to define the stroke characteristics.

