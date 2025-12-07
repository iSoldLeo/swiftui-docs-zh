--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeView/stroke(_:style:antialiased:)

抓取时间：2025-12-03T05:38:23Z

---

# stroke(_:style:antialiased:)

**实例方法**

使用颜色或渐变描绘此形状的轮廓。

## 声明

```swift
nonisolated func stroke<S>(_ content: S, style: StrokeStyle, antialiased: Bool = true) -> StrokeShapeView<Self.Content, S, Self> where S : ShapeStyle
```

## 参数

- **content**：用于描绘此形状的颜色或渐变。

- **style**：决定如何渲染此形状的描边特征，例如线条宽度以及描边是否为虚线。

## 返回值

一个带有描边的形状。

## 讨论

以下示例为 `Capsule` 添加紫色虚线描边：

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

## 修改形状

- **fill(_:style:)**：用颜色或渐变填充此形状。

- **stroke(_:lineWidth:antialiased:)**：用颜色或渐变描绘此形状的轮廓。

- **strokeBorder(_:style:antialiased:)**：返回一个视图，该视图是将此视图内缩至其样式线宽的一半后的结果。

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是使用此视图的内部描边填充您提供的内容后的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeView/stroke(_:style:antialiased:)
crawled: 2025-12-03T05:38:23Z
---

# stroke(_:style:antialiased:)

**Instance Method**

Traces the outline of this shape with a color or gradient.

## Declaration

```swift
nonisolated func stroke<S>(_ content: S, style: StrokeStyle, antialiased: Bool = true) -> StrokeShapeView<Self.Content, S, Self> where S : ShapeStyle
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

## Modify the shape

- **fill(_:style:)**: Fills this shape with a color or gradient.
- **stroke(_:lineWidth:antialiased:)**: Traces the outline of this shape with a color or gradient.
- **strokeBorder(_:style:antialiased:)**: Returns a view that’s the result of insetting this view by half of its style’s line width.
- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that’s the result of filling an inner stroke of this view with the content you supply.

