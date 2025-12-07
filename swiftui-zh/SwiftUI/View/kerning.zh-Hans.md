--- 来源：https://developer.apple.com/documentation/SwiftUI/View/kerning(_:)

抓取时间：2025-11-30T21:20:12Z

---

# kerning(_:)

**实例方法**

设置此视图中文本字符之间的间距，即字距调整。

## 声明

```swift
nonisolated func kerning(_ kerning: CGFloat) -> some View

```

## 参数

- **kerning**：文本中各个字符之间的间距。值为 `0` 时，字距调整将设置为系统默认值。

## 返回值

一个包含指定字距调整的文本的视图。

## 管理文本布局

- **truncationMode(_:)**：设置过长文本行的截断模式，使其无法在可用空间内显示。

- **truncationMode**：此值指示布局如何截断文本的最后一行以适应可用空间。

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以使其适应一行。

- **allowsTightening**：布尔值，指示是否应缩小字符间距以使文本适应可用空间。

- **minimumScaleFactor(_:)**：设置此视图中的文本缩小以适应可用空间的最小比例。

- **minimumScaleFactor**：缩小字体大小以适应可用空间的最小允许比例。

- **baselineOffset(_:)**：设置此视图中文本相对于其基线的垂直偏移量。

- **tracking(_:)**：设置此视图中文本的字距。

- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。

- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/kerning(_:)
crawled: 2025-11-30T21:20:12Z
---

# kerning(_:)

**Instance Method**

Sets the spacing, or kerning, between characters for the text in this view.

## Declaration

```swift
nonisolated func kerning(_ kerning: CGFloat) -> some View

```

## Parameters

- **kerning**: The spacing to use between individual characters in text. Value of `0` sets the kerning to the system default value.

## Return Value

A view where text has the specified amount of kerning.

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

