--- 来源：https://developer.apple.com/documentation/SwiftUI/View/truncationMode(_:)

抓取时间：2025-11-30T21:20:07Z

---

# truncationMode(_:)

**实例方法**

设置文本行长度超过可用空间时的截断模式。

## 声明

```swift
nonisolated func truncationMode(_ mode: Text.TruncationMode) -> some View

```

## 参数

- **mode**：截断模式，用于指定文本视图中文本的截断位置（如果需要）。您可以选择在文本视图的开头、中间或结尾进行截断。

## 返回值

返回一个视图，该视图会根据您选择的模式在文本行的不同位置进行截断。

## 讨论

使用 `truncationMode(_:)` 修饰符来确定长行文本是在开头、中间还是结尾被截断。截断会在删除文本时在行尾添加省略号 (…) 以提示读者文本缺失。

在下面的示例中，文本视图的边界限制了视图显示的文本量，而 `truncationMode(_:)` 指定了截断指示器的显示方向和位置：

```swift
Text("This is a block of text that will show up in a text element as multiple lines. The text will fill the available space, and then, eventually, be truncated.")
    .frame(width: 150, height: 150)
    .truncationMode(.tail)
```

## 管理文本布局

- **truncationMode**：此值指示布局如何截断最后一行文本以适应可用空间。

- **allowsTightening(_:)**：设置此视图中的文本是否可以在必要时压缩字符间距以适应一行。

- **allowsTightening**：一个布尔值，指示是否应缩小字符间距以使文本适应可用空间。

- **minimumScaleFactor(_:)**：设置此视图中文本缩小以适应可用空间的最小比例。

- **minimumScaleFactor**：缩小字体大小以适应可用空间的最小允许比例。

- **baselineOffset(_:)**：设置此视图中文本相对于其基线的垂直偏移量。

- **kerning(_:)**：设置此视图中文本的字符间距（或字距调整）。

- **tracking(_:)**：设置此视图中文本的字距。

- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。

- **TextAlignment**：文本沿水平轴的对齐位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/truncationMode(_:)
crawled: 2025-11-30T21:20:07Z
---

# truncationMode(_:)

**Instance Method**

Sets the truncation mode for lines of text that are too long to fit in the available space.

## Declaration

```swift
nonisolated func truncationMode(_ mode: Text.TruncationMode) -> some View

```

## Parameters

- **mode**: The truncation mode that specifies where to truncate the text within the text view, if needed. You can truncate at the beginning, middle, or end of the text view.

## Return Value

A view that truncates text at different points in a line depending on the mode you select.

## Discussion

Use the `truncationMode(_:)` modifier to determine whether text in a long line is truncated at the beginning, middle, or end. Truncation is indicated by adding an ellipsis (…) to the line when removing text to indicate to readers that text is missing.

In the example below, the bounds of text view constrains the amount of text that the view displays and the `truncationMode(_:)` specifies from which direction and where to display the truncation indicator:

```swift
Text("This is a block of text that will show up in a text element as multiple lines. The text will fill the available space, and then, eventually, be truncated.")
    .frame(width: 150, height: 150)
    .truncationMode(.tail)
```



## Managing text layout

- **truncationMode**: A value that indicates how the layout truncates the last line of text to fit into the available space.
- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **allowsTightening**: A Boolean value that indicates whether inter-character spacing should tighten to fit the text into the available space.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **minimumScaleFactor**: The minimum permissible proportion to shrink the font size to fit the text into the available space.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **TextAlignment**: An alignment position for text along the horizontal axis.

