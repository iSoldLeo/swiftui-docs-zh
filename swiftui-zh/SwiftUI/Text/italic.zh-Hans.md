--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/italic(_:)

抓取时间：2025-12-02T21:48:25Z

---

# italic(_:)

**实例方法**

为文本应用斜体。

## 声明

```swift
nonisolated func italic(_ isActive: Bool) -> Text
```

## 参数

- **isActive**：一个布尔值，指示是否添加斜体样式。

## 返回值

斜体文本。

## 设置视图文本的样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：为文本字体应用粗体或强调效果。

- **bold(_:)**：将文本设置为粗体。

- **italic()**：将文本设置为斜体。

- **strikethrough(_:color:)**：将文本设置为删除线。

- **strikethrough(_:pattern:color:)**：将文本设置为删除线。

- **underline(_:color:)**：将文本设置为下划线。

- **underline(_:pattern:color:)**：将文本设置为下划线。

- **monospaced(_:)**：如果可能，将文本字体更改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体更改为使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/italic(_:)
crawled: 2025-12-02T21:48:25Z
---

# italic(_:)

**Instance Method**

Applies italics to the text.

## Declaration

```swift
nonisolated func italic(_ isActive: Bool) -> Text
```

## Parameters

- **isActive**: A Boolean value that indicates whether italic styling is added.

## Return Value

Italic text.

## Styling the view’s text

- **foregroundStyle(_:)**: Sets the style of the text displayed by this view.
- **bold()**: Applies a bold or emphasized treatment to the fonts of the text.
- **bold(_:)**: Applies a bold font weight to the text.
- **italic()**: Applies italics to the text.
- **strikethrough(_:color:)**: Applies a strikethrough to the text.
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

