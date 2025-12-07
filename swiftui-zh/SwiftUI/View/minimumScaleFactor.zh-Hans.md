--- 来源：https://developer.apple.com/documentation/SwiftUI/View/minimumScaleFactor(_:)

抓取时间：2025-11-30T21:20:10Z

---

# minimumScaleFactor(_:)

**实例方法**

设置此视图中文本缩放以适应可用空间的最小量。

## 声明

```swift
nonisolated func minimumScaleFactor(_ factor: CGFloat) -> some View

```

## 参数

- **factor**：一个介于 0 和 1 之间的分数（包含 0 和 1），用于指定此视图允许的最小文本缩放量。

## 返回值

一个限制文本缩放量的视图。

## 说明

如果放置在视图中的文本无法完全容纳，并且允许文本缩小以适应空间，请使用 `minimumScaleFactor(_:)` 修饰符。例如，最小缩放因子为 `0.5` 的标签，必要时会以实际字体大小的一半来绘制文本。

在下面的示例中，[HStack](../HStack.zh-Hans.md) 包含一个行数限制为 `1` 的标签 [Text](../Text.zh-Hans.md)，该标签紧邻 [TextField](../TextField.zh-Hans.md)。为了使标签能够适应可用空间，`minimumScaleFactor(_:)` 修饰符会根据需要缩小文本以适应可用空间。

```swift
HStack {
    Text("This is a long label that will be scaled to fit:")
        .lineLimit(1)
        .minimumScaleFactor(0.5)
    TextField("My Long Text Field", text: $myTextField)
}
```

## 管理文本布局

- **truncationMode(_:)**：设置过长文本行的截断模式，使其无法适应可用空间。

- **truncationMode**：此值指示布局如何截断文本的最后一行以适应可用空间。

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以使其适应一行。

- **allowsTightening**：此布尔值指示是否应缩小字符间距以使文本适应可用空间。

- **minimumScaleFactor**：缩小字体大小以使文本适应可用空间的最小允许比例。

- **baselineOffset(_:)**：设置此视图中文本相对于其基线的垂直偏移量。

- **kerning(_:)**：设置此视图中文本的字符间距（或字距调整）。

- **tracking(_:)**：设置此视图中文本的字距。

- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。

- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/minimumScaleFactor(_:)
crawled: 2025-11-30T21:20:10Z
---

# minimumScaleFactor(_:)

**Instance Method**

Sets the minimum amount that text in this view scales down to fit in the available space.

## Declaration

```swift
nonisolated func minimumScaleFactor(_ factor: CGFloat) -> some View

```

## Parameters

- **factor**: A fraction between 0 and 1 (inclusive) you use to specify the minimum amount of text scaling that this view permits.

## Return Value

A view that limits the amount of text downscaling.

## Discussion

Use the `minimumScaleFactor(_:)` modifier if the text you place in a view doesn’t fit and it’s okay if the text shrinks to accommodate. For example, a label with a minimum scale factor of `0.5` draws its text in a font size as small as half of the actual font if needed.

In the example below, the [HStack](../HStack.zh-Hans.md) contains a [Text](../Text.zh-Hans.md) label with a line limit of `1`, that is next to a [TextField](../TextField.zh-Hans.md). To allow the label to fit into the available space, the `minimumScaleFactor(_:)` modifier shrinks the text as needed to fit into the available space.

```swift
HStack {
    Text("This is a long label that will be scaled to fit:")
        .lineLimit(1)
        .minimumScaleFactor(0.5)
    TextField("My Long Text Field", text: $myTextField)
}
```



## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

