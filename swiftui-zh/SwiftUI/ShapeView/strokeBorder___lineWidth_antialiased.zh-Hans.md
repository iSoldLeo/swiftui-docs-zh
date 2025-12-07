--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeView/strokeBorder(_:lineWidth:antialiased:)

抓取时间：2025-12-03T05:38:25Z

---

# strokeBorder(_:lineWidth:antialiased:)

**实例方法**

返回一个视图，该视图是使用您提供的内容填充其内部描边后的结果。

## 声明

```swift
nonisolated func strokeBorder<S>(_ content: S = .foreground, lineWidth: CGFloat = 1, antialiased: Bool = true) -> StrokeBorderShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## 说明

这等价于将 `self` 内缩 `lineWidth / 2`，然后使用 `lineWidth` 作为线宽为所得形状添加描边。

## 修改形状

- **fill(_:style:)**：使用颜色或渐变填充此形状。

- **stroke(_:style:antialiased:)**：用颜色或渐变勾勒此形状的轮廓。

- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变勾勒此形状的轮廓。

- **strokeBorder(_:style:antialiased:)**：返回一个视图，该视图是将此视图内缩至其样式线宽的一半后的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeView/strokeBorder(_:lineWidth:antialiased:)
crawled: 2025-12-03T05:38:25Z
---

# strokeBorder(_:lineWidth:antialiased:)

**Instance Method**

Returns a view that’s the result of filling an inner stroke of this view with the content you supply.

## Declaration

```swift
nonisolated func strokeBorder<S>(_ content: S = .foreground, lineWidth: CGFloat = 1, antialiased: Bool = true) -> StrokeBorderShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## Discussion

This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.

## Modify the shape

- **fill(_:style:)**: Fills this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **strokeBorder(_:style:antialiased:)**: Returns a view that’s the result of insetting this view by half of its style’s line width.

