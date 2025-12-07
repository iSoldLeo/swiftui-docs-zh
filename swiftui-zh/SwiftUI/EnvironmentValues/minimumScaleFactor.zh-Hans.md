---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/minimumScaleFactor
抓取时间： 2025-12-02T17:35:03Z
---

# minimumScaleFactor

**实例属性**

最小允许比例，用于缩小字体大小，使文本适合可用空间。

## 声明

```swift
var minimumScaleFactor: CGFloat { get set }
```

## 讨论

在下面的示例中，一个`minimumScaleFactor`为`0.5`的标签，为适应文本输入框旁边的空间，其文本的字体大小小到实际字体的一半：

```swift
HStack {
    Text("This is a very long label:")
        .lineLimit(1)
        .minimumScaleFactor(0.5)
    TextField("My Long Text Field", text: $myTextField)
        .frame(width: 250, height: 50, alignment: .center)
}
```



您可以将最小比例因子设置为大于 `0`、小于或等于 `1`的任意值。默认值为 `1`。

当视图中不适合缩小文本时，SwiftUI 会使用此值来缩小文本。例如，如果需要，`minimumScaleFactor` 为 `0.5` 的标签会以小到实际字体一半的字体大小绘制文本。

## 管理文本布局

- **truncationMode(_:)**：为过长的文本行设置截断模式。
- **truncationMode**：表示布局如何截断最后一行文本以适应可用空间的值。
- **allowsTightening(_:)**：设置该视图中的文本是否可以在必要时压缩字符之间的空格，以适应一行中的文本。
- **allowsTightening**：布尔值，用于指示是否应压缩字符间距，以使文本适合可用空间。
- **minimumScaleFactor(_:)**：设置该视图中文本缩小以适应可用空间的最小量。
- **baselineOffset(_:)**：设置该视图中文本相对于其基线的垂直偏移量。
- **kerning(_:)**：为该视图中的文本设置字符间距或字间距。
- **tracking(_:)**：设置该视图中文本的跟踪。
- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。
- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/minimumScaleFactor
crawled: 2025-12-02T17:35:03Z
---

# minimumScaleFactor

**Instance Property**

The minimum permissible proportion to shrink the font size to fit the text into the available space.

## Declaration

```swift
var minimumScaleFactor: CGFloat { get set }
```

## Discussion

In the example below, a label with a `minimumScaleFactor` of `0.5` draws its text in a font size as small as half of the actual font if needed to fit into the space next to the text input field:

```swift
HStack {
    Text("This is a very long label:")
        .lineLimit(1)
        .minimumScaleFactor(0.5)
    TextField("My Long Text Field", text: $myTextField)
        .frame(width: 250, height: 50, alignment: .center)
}
```



You can set the minimum scale factor to any value greater than `0` and less than or equal to `1`. The default value is `1`.

SwiftUI uses this value to shrink text that doesn’t fit in a view when it’s okay to shrink the text. For example, a label with a `minimumScaleFactor` of `0.5` draws its text in a font size as small as half the actual font if needed.

## Managing text layout

- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

