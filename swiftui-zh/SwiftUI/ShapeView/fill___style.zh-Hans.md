--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeView/fill(_:style:)

抓取时间：2025-12-03T05:38:22Z

---

# fill(_:style:)

**实例方法**

使用颜色或渐变填充此形状。

## 声明

```swift
nonisolated func fill<S>(_ content: S = .foreground, style: FillStyle = FillStyle()) -> FillShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## 参数

- **content**：填充此形状时使用的颜色或渐变。

- **style**：决定填充渲染方式的样式选项。

## 返回值

使用您提供的颜色或渐变填充的形状。

## 修改形状

- **stroke(_:style:antialiased:)**：使用颜色或渐变描绘此形状的轮廓。

- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变勾勒出此形状的轮廓。

- **strokeBorder(_:style:antialiased:)**：返回一个视图，该视图是将此视图内缩至其样式线宽的一半后的结果。

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是将此视图的内描边填充您提供的内容后的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeView/fill(_:style:)
crawled: 2025-12-03T05:38:22Z
---

# fill(_:style:)

**Instance Method**

Fills this shape with a color or gradient.

## Declaration

```swift
nonisolated func fill<S>(_ content: S = .foreground, style: FillStyle = FillStyle()) -> FillShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## Parameters

- **content**: The color or gradient to use when filling this shape.
- **style**: The style options that determine how the fill renders.

## Return Value

A shape filled with the color or gradient you supply.

## Modify the shape

- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **strokeBorder(_:style:antialiased:)**: Returns a view that’s the result of insetting this view by half of its style’s line width.
- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that’s the result of filling an inner stroke of this view with the content you supply.

