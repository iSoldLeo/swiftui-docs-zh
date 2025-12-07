--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/tracking(_:)

抓取时间：2025-12-02T21:48:30Z

---

# tracking(_:)

**实例方法**

设置文本的字距。

## 声明

```swift
nonisolated func tracking(_ tracking: CGFloat) -> Text
```

## 参数

- **tracking**：布局后，视图应在每个字符簇中添加的额外间距（以点为单位）。`0` 的值会将字距设置为系统默认值。

## 返回值

具有指定字距的文本。

## 说明

字距会在文本视图中的字符之间添加间距（以点为单位）。正值会增加字符之间的间距，而负值会使字符之间的间距缩小。

```swift
VStack(alignment: .leading) {
    Text("ABCDEF").tracking(-3)
    Text("ABCDEF")
    Text("ABCDEF").tracking(3)
}
```

上面的代码使用了异常大的字距调整量，以便于观察效果。

字距调整的效果类似于 [kerning(_:)](kerning.zh-Hans.md) 修饰符，但它添加或删除的是尾随空格，而不是改变字符偏移量。此外，使用任何非零值的字距调整都会禁用非必要的连字，而字距调整则会尝试保留连字。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体字重。

- **italic()**：对文本应用斜体。

- **italic(_:)**：文本设置为斜体。

- **strikethrough(_:color:)**：文本添加删除线。

- **strikethrough(_:pattern:color:)**：文本添加删除线。

- **underline(_:color:)**：文本添加下划线。

- **underline(_:pattern:color:)**：文本添加下划线。

- **monospaced(_:)**：如果可能，将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体修改为使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **baselineOffset(_:)**：设置文本相对于其基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/tracking(_:)
crawled: 2025-12-02T21:48:30Z
---

# tracking(_:)

**Instance Method**

Sets the tracking for the text.

## Declaration

```swift
nonisolated func tracking(_ tracking: CGFloat) -> Text
```

## Parameters

- **tracking**: The amount of additional space, in points, that the view should add to each character cluster after layout. Value of `0` sets the tracking to the system default value.

## Return Value

Text with the specified amount of tracking.

## Discussion

Tracking adds space, measured in points, between the characters in the text view. A positive value increases the spacing between characters, while a negative value brings the characters closer together.

```swift
VStack(alignment: .leading) {
    Text("ABCDEF").tracking(-3)
    Text("ABCDEF")
    Text("ABCDEF").tracking(3)
}
```

The code above uses an unusually large amount of tracking to make it easy to see the effect.



The effect of tracking resembles that of the [kerning(_:)](kerning.zh-Hans.md) modifier, but adds or removes trailing whitespace, rather than changing character offsets. Also, using any nonzero amount of tracking disables nonessential ligatures, whereas kerning attempts to maintain ligatures.



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
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

