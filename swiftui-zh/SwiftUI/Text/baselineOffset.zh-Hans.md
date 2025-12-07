--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/baselineOffset(_:)

抓取时间：2025-12-02T21:48:31Z

---

# baselineOffset(_:)

**实例方法**

设置文本相对于其基线的垂直偏移量。

## 声明

```swift
nonisolated func baselineOffset(_ baselineOffset: CGFloat) -> Text
```

## 参数

- **baselineOffset**：文本相对于其基线的垂直偏移量（向上或向下）。

## 返回值

文本位于其基线上方或下方的位置。

## 说明

更改基线偏移量，使视图中的文本相对于其基线向上或向下移动（以点为单位）。视图的边界会扩展以包含移动后的文本。

```swift
HStack(alignment: .top) {
    Text("Hello")
        .baselineOffset(-10)
        .border(Color.red)
    Text("Hello")
        .border(Color.green)
    Text("Hello")
        .baselineOffset(10)
        .border(Color.blue)
}
.background(Color(white: 0.9))
```

通过在每个文本视图周围绘制边框，您可以观察文本的移动方式及其对视图的影响。

第一个视图（偏移量为负）会向下扩展以适应降低的文本。最后一个视图（偏移量为正）会向上扩展。外层的 [HStack](../HStack.zh-Hans.md) 实例（以灰色显示）确保所有文本视图的顶部边缘始终保持对齐，而与偏移量无关。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体字重。

- **italic()**：对文本应用斜体。

- **italic(_:)**：文本应用斜体。

- **strikethrough(_:color:)**：文本应用删除线。

- **strikethrough(_:pattern:color:)**：文本应用删除线。

- **underline(_:color:)**：文本应用下划线。

- **underline(_:pattern:color:)**：文本应用下划线。

- **monospaced(_:)**：尽可能将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体修改为使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/baselineOffset(_:)
crawled: 2025-12-02T21:48:31Z
---

# baselineOffset(_:)

**Instance Method**

Sets the vertical offset for the text relative to its baseline.

## Declaration

```swift
nonisolated func baselineOffset(_ baselineOffset: CGFloat) -> Text
```

## Parameters

- **baselineOffset**: The amount to shift the text vertically (up or down) relative to its baseline.

## Return Value

Text that’s above or below its baseline.

## Discussion

Change the baseline offset to move the text in the view (in points) up or down relative to its baseline. The bounds of the view expand to contain the moved text.

```swift
HStack(alignment: .top) {
    Text("Hello")
        .baselineOffset(-10)
        .border(Color.red)
    Text("Hello")
        .border(Color.green)
    Text("Hello")
        .baselineOffset(10)
        .border(Color.blue)
}
.background(Color(white: 0.9))
```

By drawing a border around each text view, you can see how the text moves, and how that affects the view.



The first view, with a negative offset, grows downward to handle the lowered text. The last view, with a positive offset, grows upward. The enclosing [HStack](../HStack.zh-Hans.md) instance, shown in gray, ensures all the text views remain aligned at their top edge, regardless of the offset.

## Styling the view’s text

- **foregroundStyle(_:)**: Sets the style of the text displayed by this view.
- **bold()**: Applies a bold or emphasized treatment to the fonts of the text.
- **bold(_:)**: Applies a bold font weight to the text.
- **italic()**: Applies italics to the text.
- **italic(_:)**: Applies italics to the text.
- **strikethrough(_:color:)**: Applies a strikethrough to the text.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text.
- **underline(_:color:)**: Applies an underline to the text.
- **underline(_:pattern:color:)**: Applies an underline to the text.
- **monospaced(_:)**: Modifies the font of the text to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the text view’s font to use fixed-width digits, while leaving other characters proportionally spaced.
- **kerning(_:)**: Sets the spacing, or kerning, between characters.
- **tracking(_:)**: Sets the tracking for the text.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

