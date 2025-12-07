---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/stroke(_:lineWidth:antialiased:)
抓取时间：2025-12-02T21:41:54Z
---

# stroke(_:lineWidth:antialiased:)

**实例方法**

使用颜色或梯度描边此形状的轮廓。

## 声明

```swift
nonisolated func stroke<S>(_ content: S, lineWidth: CGFloat = 1, antialiased: Bool = true) -> StrokeShapeView<Self, S, EmptyView> where S : ShapeStyle
```

## 参数

- **content**：用于描边此形状的颜色或渐变色。
- **lineWidth**：勾画此形状的笔划宽度。

## 返回值

有描边的形状。

## 讨论

下面的示例绘制了一个带有紫色描边的圆：

```swift
Circle().stroke(Color.purple, lineWidth: 5)
```

## 设置笔划特性

- **stroke(_:lineWidth:)**：用颜色或渐变描边该形状的轮廓。
- **stroke(lineWidth:)**：返回一个新形状，它是`self` 的描边副本，线宽由 `lineWidth` 定义，`StrokeStyle` 的所有其他属性均为默认值。
- **stroke(_:style:)**：用颜色或梯度描边该形状的轮廓。
- **stroke(_:style:antialiased:)**：用颜色或渐变描出该形状的轮廓。
- **stroke(style:)**：使用`style` 的内容定义描边特征，返回一个新形状，它是`self` 的描边副本。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/stroke(_:lineWidth:antialiased:)
crawled: 2025-12-02T21:41:54Z
---

# stroke(_:lineWidth:antialiased:)

**Instance Method**

Traces the outline of this shape with a color or gradient.

## Declaration

```swift
nonisolated func stroke<S>(_ content: S, lineWidth: CGFloat = 1, antialiased: Bool = true) -> StrokeShapeView<Self, S, EmptyView> where S : ShapeStyle
```

## Parameters

- **content**: The color or gradient with which to stroke this shape.
- **lineWidth**: The width of the stroke that outlines this shape.

## Return Value

A stroked shape.

## Discussion

The following example draws a circle with a purple stroke:

```swift
Circle().stroke(Color.purple, lineWidth: 5)
```

## Setting the stroke characteristics

- **stroke(_:lineWidth:)**: Traces the outline of this shape with a color or gradient.
- **stroke(lineWidth:)**: Returns a new shape that is a stroked copy of `self` with line-width defined by `lineWidth` and all other properties of `StrokeStyle` having their default values.
- **stroke(_:style:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(style:)**: Returns a new shape that is a stroked copy of `self`, using the contents of `style` to define the stroke characteristics.

