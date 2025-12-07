--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/DateStyle
抓取时间：2025-12-02T21:48:33Z

---

# Text.DateStyle

**Structure**

用于显示日期的预定义样式。

## 声明

```swift
struct DateStyle
```

## 获取文本日期样式

- **date**：显示日期的样式。

- **offset**：显示日期相对于当前时间的偏移量的样式。

- **relative**：显示日期相对于当前时间的样式。

- **time**：仅显示日期时间部分的样式。

- **timer**：一种将日期显示为倒计时的样式，从当前时间开始计时。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体。

- **italic()**：对文本应用斜体。

- **italic(_:)**：对文本应用斜体。

- **strikethrough(_:color:)**：对文本应用删除线。

- **strikethrough(_:pattern:color:)**：对文本应用删除线。

- **underline(_:color:)**：为文本添加下划线。

- **underline(_:pattern:color:)**：为文本添加下划线。

- **monospaced(_:)**：尽可能将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体修改为使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：一种用于转换文本中字符大小写的方案。

## 符合以下标准

- Copyable

- Decodable

- Encodable

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/DateStyle
crawled: 2025-12-02T21:48:33Z
---

# Text.DateStyle

**Structure**

A predefined style used to display a `Date`.

## Declaration

```swift
struct DateStyle
```

## Getting text date styles

- **date**: A style displaying a date.
- **offset**: A style displaying a date as offset from now.
- **relative**: A style displaying a date as relative to now.
- **time**: A style displaying only the time component for a date.
- **timer**: A style displaying a date as timer counting from now.

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
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.

## Conforms To

- Copyable
- Decodable
- Encodable
- Equatable
- Sendable
- SendableMetatype

