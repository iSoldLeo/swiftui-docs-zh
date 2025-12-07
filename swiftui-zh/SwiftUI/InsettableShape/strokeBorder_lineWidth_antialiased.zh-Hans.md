---
来源：https://developer.apple.com/documentation/SwiftUI/InsettableShape/strokeBorder(lineWidth:antialiased:)
抓取时间：2025-12-03T05:37:32Z
---

# strokeBorder(lineWidth:antialiased:)

**实例方法**

返回一个视图，该视图是用前景色填充`lineWidth`大小的边框（又称内边框）的结果。这相当于用`lineWidth / 2`嵌入`self`，并用`lineWidth`作为线宽描边。

## 声明

```swift
func strokeBorder(lineWidth: CGFloat = 1, antialiased: Bool = true) -> some View

```

## 设置笔触边框特征

- **strokeBorder(_:lineWidth:antialiased:)**：返回一个视图，该视图是用`content`填充`self`的`lineWidth`大小的边框（又称内描边）的结果。这相当于用`lineWidth / 2`嵌入`self`，并用`lineWidth`作为线宽描边得到的形状。
- **strokeBorder(_:style:antialiased:)**：返回一个视图，该视图是用`self`嵌入`style.lineWidth / 2`，用`style`描边得到的形状，然后用`content`填充。
- **strokeBorder(style:antialiased:)**：返回用`style.lineWidth / 2`嵌入`self`后得到的视图，用`style`描边，然后填充前景色。


---
source: https://developer.apple.com/documentation/SwiftUI/InsettableShape/strokeBorder(lineWidth:antialiased:)
crawled: 2025-12-03T05:37:32Z
---

# strokeBorder(lineWidth:antialiased:)

**Instance Method**

Returns a view that is the result of filling the `lineWidth`-sized border (aka inner stroke) of `self` with the foreground color. This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.

## Declaration

```swift
func strokeBorder(lineWidth: CGFloat = 1, antialiased: Bool = true) -> some View

```

## Setting the stroke border characteristics

- **strokeBorder(_:lineWidth:antialiased:)**: Returns a view that is the result of filling the `lineWidth`-sized border (aka inner stroke) of `self` with `content`. This is equivalent to insetting `self` by `lineWidth / 2` and stroking the resulting shape with `lineWidth` as the line-width.
- **strokeBorder(_:style:antialiased:)**: Returns a view that is the result of insetting `self` by `style.lineWidth / 2`, stroking the resulting shape with `style`, and then filling with `content`.
- **strokeBorder(style:antialiased:)**: Returns a view that is the result of insetting `self` by `style.lineWidth / 2`, stroking the resulting shape with `style`, and then filling with the foreground color.

