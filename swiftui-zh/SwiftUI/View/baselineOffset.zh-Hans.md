--- 来源：https://developer.apple.com/documentation/SwiftUI/View/baselineOffset(_:)

抓取时间：2025-11-30T21:20:11Z

---

# baselineOffset(_:)

**实例方法**

设置此视图中文本相对于其基线的垂直偏移量。

## 声明

```swift
nonisolated func baselineOffset(_ baselineOffset: CGFloat) -> some View

```

## 参数

- **baselineOffset**：文本相对于其基线垂直（向上或向下）移动的量。

## 返回值

文本位于其基线上方或下方的视图。

## 管理文本布局

- **truncationMode(_:)**：设置过长文本行的截断模式，使其无法在可用空间内显示。

- **truncationMode**：此值指示布局如何截断文本的最后一行以适应可用空间。

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以适应一行。

- **allowsTightening**：布尔值，指示是否应缩小字符间距以适应可用空间。

- **minimumScaleFactor(_:)**：设置此视图中的文本缩小以适应可用空间的最小比例。

- **minimumScaleFactor**：缩小字体大小以适应可用空间的最小允许比例。

- **kerning(_:)**：设置此视图中文本的字符间距（或字距调整）。

- **tracking(_:)**：设置此视图中文本的字距。

- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。

- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/baselineOffset(_:)
crawled: 2025-11-30T21:20:11Z
---

# baselineOffset(_:)

**Instance Method**

Sets the vertical offset for the text relative to its baseline in this view.

## Declaration

```swift
nonisolated func baselineOffset(_ baselineOffset: CGFloat) -> some View

```

## Parameters

- **baselineOffset**: The amount to shift the text vertically (up or down) relative to its baseline.

## Return Value

A view where text is above or below its baseline.

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

