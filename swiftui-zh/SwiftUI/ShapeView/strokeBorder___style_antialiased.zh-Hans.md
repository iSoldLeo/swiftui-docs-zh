--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeView/strokeBorder(_:style:antialiased:)

抓取时间：2025-12-01T10:27:33Z

---

# strokeBorder(_:style:antialiased:)

**实例方法**

返回一个视图，该视图是将此视图内缩至其样式线宽的一半后的结果。

## 声明

```swift
nonisolated func strokeBorder<S>(_ content: S = .foreground, style: StrokeStyle, antialiased: Bool = true) -> StrokeBorderShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## 说明

此方法使用 `style` 描边，并使用 `content` 填充。

## 修改形状

- **fill(_:style:)**：使用颜色或渐变填充此形状。

- **stroke(_:style:antialiased:)**：用颜色或渐变勾勒此形状的轮廓。

- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变勾勒此形状的轮廓。

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是将您提供的内容填充到此视图的内描边后的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeView/strokeBorder(_:style:antialiased:)
crawled: 2025-12-01T10:27:33Z
---

# strokeBorder(_:style:antialiased:)

**Instance Method**

Returns a view that’s the result of insetting this view by half of its style’s line width.

## Declaration

```swift
nonisolated func strokeBorder<S>(_ content: S = .foreground, style: StrokeStyle, antialiased: Bool = true) -> StrokeBorderShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## Discussion

This method strokes the resulting shape with `style` and fills it with `content`.

## Modify the shape

- **fill(_:style:)**: Fills this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that’s the result of filling an inner stroke of this view with the content you supply.

