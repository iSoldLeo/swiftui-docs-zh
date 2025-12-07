--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/monospaced(_:)

抓取时间：2025-12-01T02:39:19Z

---

# monospaced(_:)

**实例方法**

尽可能将文本的字体更改为当前字体的等宽版本。

## 声明

```swift
nonisolated func monospaced(_ isActive: Bool = true) -> Text
```

## 参数

- **isActive**：一个布尔值，指示是否添加等宽样式。默认值为 `true`。

## 返回值

等宽文本。

## 设置视图文本的样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体。

- **italic()**：对文本应用斜体。

- **italic(_:)**：对文本应用斜体。

- **strikethrough(_:color:)**：对文本应用删除线。

- **strikethrough(_:pattern:color:)**：对文本应用删除线。

- **underline(_:color:)**：对文本应用下划线。

- **underline(_:pattern:color:)**：对文本应用下划线。

- **monospacedDigit()**：修改文本视图的字体，使其使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/monospaced(_:)
crawled: 2025-12-01T02:39:19Z
---

# monospaced(_:)

**Instance Method**

Modifies the font of the text to use the fixed-width variant of the current font, if possible.

## Declaration

```swift
nonisolated func monospaced(_ isActive: Bool = true) -> Text
```

## Parameters

- **isActive**: A Boolean value that indicates whether monospaced styling is added. Default value is `true`.

## Return Value

Monospaced text.

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
- **monospacedDigit()**: Modifies the text view’s font to use fixed-width digits, while leaving other characters proportionally spaced.
- **kerning(_:)**: Sets the spacing, or kerning, between characters.
- **tracking(_:)**: Sets the tracking for the text.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

