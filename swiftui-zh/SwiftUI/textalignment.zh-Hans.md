---
来源： https://developer.apple.com/documentation/swiftui/textalignment
抓取时间： 2025-12-04T13:20:49Z
---

# 文本对齐方式

**Enumeration**

文本沿水平轴的对齐位置。

## 声明

```swift
@frozen enum TextAlignment
```

## 获取文本排列

- **TextAlignment.center**
- **TextAlignment.leading**
- **TextAlignment.trailing**

## 管理文本布局

- **truncationMode(_:)**：为过长的文本行设置截断模式。
- **truncationMode**：表示布局如何截断最后一行文本以适应可用空间的值。
- **allowsTightening(_:)**：设置该视图中的文本是否可以在必要时压缩字符之间的空格，以适应一行中的文本。
- **allowsTightening**：布尔值，用于指示是否应压缩字符间距，以使文本适合可用空间。
- **minimumScaleFactor(_:)**：设置该视图中文本缩小以适应可用空间的最小量。
- **minimumScaleFactor**：为使文本适合可用空间而缩小字体大小的最小允许比例。
- **baselineOffset(_:)**：设置文本相对于该视图中基线的垂直偏移。
- **kerning(_:)**：为该视图中的文本设置字符间距或字间距。
- **tracking(_:)**：为该视图中的文本设置跟踪。
- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。

## 符合

- 符合
- CaseIterable
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/textalignment
crawled: 2025-12-04T13:20:49Z
---

# TextAlignment

**Enumeration**

An alignment position for text along the horizontal axis.

## Declaration

```swift
@frozen enum TextAlignment
```

## Getting text alignments

- **TextAlignment.center**
- **TextAlignment.leading**
- **TextAlignment.trailing**

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

