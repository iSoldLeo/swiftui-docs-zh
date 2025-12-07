---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/truncationMode
抓取时间： 2025-12-02T17:35:01Z
---

# 截断模式

**实例属性**

表示布局如何截断最后一行文本以适应可用空间的值。

## 声明

```swift
var truncationMode: Text.TruncationMode { get set }
```

## 讨论

默认值为 [tail](../Text/TruncationMode/tail.zh-Hans.md)。不过，某些控件可能有不同的默认值。

## 管理文本布局

- **truncationMode(_:)**：设置文本行太长无法在可用空间内容纳时的截断模式。
- **allowsTightening(_:)**：设置该视图中的文本是否可以在必要时压缩字符之间的空格，以适应一行中的文本。
- **allowsTightening**：布尔值，用于指示是否应压缩字符间距，以使文本适合可用空间。
- **minimumScaleFactor(_:)**：设置该视图中文本缩小以适应可用空间的最小量。
- **minimumScaleFactor**：为使文本适合可用空间而缩小字体大小的最小允许比例。
- **baselineOffset(_:)**：设置文本相对于该视图中基线的垂直偏移。
- **kerning(_:)**：为该视图中的文本设置字符间距或字间距。
- **tracking(_:)**：为该视图中的文本设置跟踪。
- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。
- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/truncationMode
crawled: 2025-12-02T17:35:01Z
---

# truncationMode

**Instance Property**

A value that indicates how the layout truncates the last line of text to fit into the available space.

## Declaration

```swift
var truncationMode: Text.TruncationMode { get set }
```

## Discussion

The default value is [tail](../Text/TruncationMode/tail.zh-Hans.md). Some controls, however, might have a different default if appropriate.

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

