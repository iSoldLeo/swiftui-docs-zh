--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeView/stroke(_:lineWidth:antialiased:)

抓取时间：2025-12-01T10:27:32Z

---

# stroke(_:lineWidth:antialiased:)

**实例方法**

使用颜色或渐变描绘此形状的轮廓。

## 声明

```swift
nonisolated func stroke<S>(_ content: S, lineWidth: CGFloat = 1, antialiased: Bool = true) -> StrokeShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## 参数

- **content**：用于描绘此形状的颜色或渐变。

- **lineWidth**：描绘此形状轮廓的线条宽度。

## 返回值

一个带有描边的形状。

## 讨论

以下示例绘制一个带有紫色描边的圆：

```swift
Circle().stroke(Color.purple, lineWidth: 5)
```

## 修改形状

- **fill(_:style:)**：用颜色或渐变填充此形状。

- **stroke(_:style:antialiased:)**：用颜色或渐变描绘此形状的轮廓。

- **strokeBorder(_:style:antialiased:)**：返回一个视图，该视图是将此视图内缩至其样式线宽的一半后的结果。

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是将此视图的内描边填充您提供的内容后的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeView/stroke(_:lineWidth:antialiased:)
crawled: 2025-12-01T10:27:32Z
---

# stroke(_:lineWidth:antialiased:)

**Instance Method**

Traces the outline of this shape with a color or gradient.

## Declaration

```swift
nonisolated func stroke<S>(_ content: S, lineWidth: CGFloat = 1, antialiased: Bool = true) -> StrokeShapeView<Self.Content, S, Self> where S : ShapeStyle
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

## Modify the shape

- **fill(_:style:)**: Fills this shape with a color or gradient.
- **stroke(_:style:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **strokeBorder(_:style:antialiased:)**: Returns a view that’s the result of insetting this view by half of its style’s line width.
- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that’s the result of filling an inner stroke of this view with the content you supply.

