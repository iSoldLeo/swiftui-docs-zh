--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/strikethrough(_:color:)

抓取时间：2025-12-01T02:39:17Z

---

# strikethrough(_:color:)

**实例方法**

为文本添加删除线。

## 声明

```swift
nonisolated func strikethrough(_ isActive: Bool = true, color: Color? = nil) -> Text
```

## 参数

- **isActive**：一个布尔值，指示文本是否应用了删除线。

- **color**：删除线的颜色。如果 `color` 为 `nil`，则删除线使用默认的前景色。

## 返回值

文本中间有一条删除线。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体。

- **italic()**：对文本应用斜体。

- **italic(_:)**：对文本应用斜体。

- **strikethrough(_:pattern:color:)**：对文本应用删除线。

- **underline(_:color:)**：对文本应用下划线。

- **underline(_:pattern:color:)**：对文本应用下划线。

- **monospaced(_:)**：尽可能将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：修改文本视图的字体，使其使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/strikethrough(_:color:)
crawled: 2025-12-01T02:39:17Z
---

# strikethrough(_:color:)

**Instance Method**

Applies a strikethrough to the text.

## Declaration

```swift
nonisolated func strikethrough(_ isActive: Bool = true, color: Color? = nil) -> Text
```

## Parameters

- **isActive**: A Boolean value that indicates whether the text has a strikethrough applied.
- **color**: The color of the strikethrough. If `color` is `nil`, the strikethrough uses the default foreground color.

## Return Value

Text with a line through its center.

## Styling the view’s text

- **foregroundStyle(_:)**: Sets the style of the text displayed by this view.
- **bold()**: Applies a bold or emphasized treatment to the fonts of the text.
- **bold(_:)**: Applies a bold font weight to the text.
- **italic()**: Applies italics to the text.
- **italic(_:)**: Applies italics to the text.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text.
- **underline(_:color:)**: Applies an underline to the text.
- **underline(_:pattern:color:)**: Applies an underline to the text.
- **monospaced(_:)**: Modifies the font of the text to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the text view’s font to use fixed-width digits, while leaving other characters proportionally spaced.
- **kerning(_:)**: Sets the spacing, or kerning, between characters.
- **tracking(_:)**: Sets the tracking for the text.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

