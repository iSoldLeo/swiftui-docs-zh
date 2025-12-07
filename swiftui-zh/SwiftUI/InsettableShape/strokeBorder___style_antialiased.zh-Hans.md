---
源：https://developer.apple.com/documentation/SwiftUI/InsettableShape/strokeBorder(_:style:antialiased:)
抓取时间： 2025-12-03T05:37:33Z
---

# strokeBorder(_:style:antialiased:)

**实例方法**

返回一个视图，该视图是`self`内嵌`style.lineWidth / 2`，用`style`描边，然后用`content`填充的结果。

## 声明

```swift
func strokeBorder<S>(_ content: S, style: StrokeStyle, antialiased: Bool = true) -> some View where S : ShapeStyle

```

## 设置笔触边框特征

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是用`content`填充`self`的`lineWidth`大小的边框（又称内描边）的结果。这相当于用`lineWidth / 2`嵌入`self`，并用`lineWidth`作为线宽描边得到的形状。
- **strokeBorder(lineWidth:antialiased:)**：用前景色填充`lineWidth` 大小的边框（又称内描边）后返回的视图。这相当于用`lineWidth / 2`嵌入`self`，并用`lineWidth`作为线宽描边。
- **strokeBorder(style:antialiased:)**：返回一个视图，该视图是用`style.lineWidth / 2`嵌入`self`，用`style`描边，然后填充前景色的结果。


---
source: https://developer.apple.com/documentation/SwiftUI/InsettableShape/strokeBorder(_:style:antialiased:)
crawled: 2025-12-03T05:37:33Z
---

# strokeBorder(_:style:antialiased:)

**Instance Method**

Returns a view that is the result of insetting `self` by `style.lineWidth / 2`, stroking the resulting shape with `style`, and then filling with `content`.

## Declaration

```swift
func strokeBorder<S>(_ content: S, style: StrokeStyle, antialiased: Bool = true) -> some View where S : ShapeStyle

```

## Setting the stroke border characteristics

- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that is the result of filling the `lineWidth`-sized border (aka inner stroke) of `self` with `content`. This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.
- **strokeBorder(lineWidth:antialiased:)**: Returns a view that is the result of filling the `lineWidth`-sized border (aka inner stroke) of `self` with the foreground color. This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.
- **strokeBorder(style:antialiased:)**: Returns a view that is the result of insetting `self` by `style.lineWidth / 2`, stroking the resulting shape with `style`, and then filling with the foreground color.

