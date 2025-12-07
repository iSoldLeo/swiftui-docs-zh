--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/LineStyle
抓取时间：2025-12-02T21:48:33Z

---

# Text.LineStyle

**Structure**

用于绘制 `StrikethroughStyleAttribute` 和 `UnderlineStyleAttribute` 的线条的样式描述。

## 声明

```swift
struct LineStyle
```

## 概述

使用此类型指定 `AttributedString` 的 `underlineStyle` 和 `strikethroughStyle` SwiftUI 属性。

## 获取文本线条样式

- **single**：绘制一条实线。

## 创建文本行样式

- **init(nsUnderlineStyle:)**：从 `NSUnderlineStyle` 创建 `Text.LineStyle`。

- **init(pattern:color:)**：创建行样式。

- **Text.LineStyle.Pattern**：行的图案。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold()**：对文本字体应用粗体或强调效果。

- **bold(_:)**：对文本应用粗体。

- **italic()**：对文本应用斜体。

- **italic(_:)**：为文本添加斜体。

- **strikethrough(_:color:)**：为文本添加删除线。

- **strikethrough(_:pattern:color:)**：为文本添加删除线。

- **underline(_:color:)**：为文本添加下划线。

- **underline(_:pattern:color:)**：为文本添加下划线。

- **monospaced(_:)**：尽可能将文本字体更改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体更改为使用等宽数字，同时保持其他字符按比例间距。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/LineStyle
crawled: 2025-12-02T21:48:33Z
---

# Text.LineStyle

**Structure**

Description of the style used to draw the line for `StrikethroughStyleAttribute` and `UnderlineStyleAttribute`.

## Declaration

```swift
struct LineStyle
```

## Overview

Use this type to specify `underlineStyle` and `strikethroughStyle` SwiftUI attributes of an `AttributedString`.

## Getting text line styles

- **single**: Draw a single solid line.

## Creating a text line style

- **init(nsUnderlineStyle:)**: Creates a `Text.LineStyle` from `NSUnderlineStyle`.
- **init(pattern:color:)**: Creates a line style.
- **Text.LineStyle.Pattern**: The pattern, that the line has.

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

- Equatable
- Hashable
- Sendable
- SendableMetatype

