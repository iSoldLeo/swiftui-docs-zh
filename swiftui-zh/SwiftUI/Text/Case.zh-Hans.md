--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Case
抓取时间：2025-12-02T21:48:32Z

---

# Text.Case

**Enumeration**

用于转换文本中字符大小写的方案。

## 声明

```swift
enum Case
```

## 获取文本大小写

- **Text.Case.lowercase**：全部显示小写字母。

- **Text.Case.uppercase**：全部显示大写字母。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：将文本设置为粗体。

- **italic()**：将文本设置为斜体。

- **italic(_:)**：将文本设置为斜体。

- **strikethrough(_:color:)**：将文本设置为删除线。

- **strikethrough(_:pattern:color:)**：将文本设置为删除线。

- **underline(_:color:)**：将文本设置为下划线。

- **underline(_:pattern:color:)**：将文本设置为下划线。

- **monospaced(_:)**：如果可能，将文本的字体更改为当前字体的等宽版本。

- **monospacedDigit()**：修改文本视图的字体，使其使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于其基线的垂直偏移量。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。

## 符合以下规范

- 可复制

- 可等值化

- 可哈希化

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Case
crawled: 2025-12-02T21:48:32Z
---

# Text.Case

**Enumeration**

A scheme for transforming the capitalization of characters within text.

## Declaration

```swift
enum Case
```

## Getting text cases

- **Text.Case.lowercase**: Displays text in all lowercase characters.
- **Text.Case.uppercase**: Displays text in all uppercase characters.

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
- **Text.DateStyle**: A predefined style used to display a `Date`.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

