--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/bold()

抓取时间：2025-12-02T21:48:23Z

---

# bold()

**实例方法**

对文本字体应用粗体或强调效果。

## 声明

```swift
nonisolated func bold() -> Text
```

## 返回值

粗体或强调后的文本。

## 说明

对于由文本样式创建的字体，这可能意味着应用强调样式，但这并不一定意味着特指粗体字重，因此请勿将此修饰符与 [doc://com.apple.documentation/documentation/SwiftUI/Text/fontWeight(_:)] 混淆。

例如：

```swift
Text("hello").font(.body).bold()
```

很可能会得到正文文本样式的强调版本，其字重通常为 [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/semibold]。而

```swift
Text("hello").font(.body).fontWeight(.bold)
```

将专门用于设置正文文本的字体，字重为 [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/bold]。

## 设置视图文本样式

- **foregroundStyle(_:)**：设置此视图显示的文本样式。

- **bold(_:)**：为文本应用粗体。

- **italic()**：为文本应用斜体。

- **italic(_:)**：为文本应用斜体。

- **strikethrough(_:color:)**：为文本应用删除线。

- **strikethrough(_:pattern:color:)**：为文本应用删除线。

- **underline(_:color:)**：为文本应用下划线。

- **underline(_:pattern:color:)**：为文本添加下划线。

- **monospaced(_:)**：尽可能将文本字体修改为当前字体的等宽版本。

- **monospacedDigit()**：将文本视图的字体修改为使用等宽数字，同时保持其他字符按比例间距排列。

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/bold()
crawled: 2025-12-02T21:48:23Z
---

# bold()

**Instance Method**

Applies a bold or emphasized treatment to the fonts of the text.

## Declaration

```swift
nonisolated func bold() -> Text
```

## Return Value

Bold or emphasized text.

## Discussion

For fonts created from text styles, it could mean applying emphasized styling, which does not necessarily mean the bold weight specifically, so this modifier is not to be confused with [doc://com.apple.documentation/documentation/SwiftUI/Text/fontWeight(_:)].

For example:

```swift
Text("hello").font(.body).bold()
```

will most likely get you the emphasized version of body text style, which is often in [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/semibold] weight. While

```swift
Text("hello").font(.body).fontWeight(.bold)
```

will specifically get you the body text style font in the [doc://com.apple.documentation/documentation/SwiftUI/Font/Weight/bold] weight.

## Styling the view’s text

- **foregroundStyle(_:)**: Sets the style of the text displayed by this view.
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
- **Text.DateStyle**: A predefined style used to display a `Date`.

