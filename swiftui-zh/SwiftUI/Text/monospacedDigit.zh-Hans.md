--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/monospacedDigit()

抓取时间：2025-12-01T02:39:20Z

---

# monospacedDigit()

**实例方法**

修改文本视图的字体，使其使用等宽数字，而其他字符保持比例间距。

## 声明

```swift
nonisolated func monospacedDigit() -> Text
```

## 返回值

一个使用等宽数字字符、其他字符保持比例间距的文本视图。

## 说明

此修饰符仅影响数字字符，其他字符保持不变。

以下示例展示了 `monospacedDigit()` 对文本视图的影响。它在 [VStack](../VStack.zh-Hans.md) 中排列两个文本视图，每个视图都显示一个格式化的日期，其中包含多个字符 1。第二个文本视图使用 `monospacedDigit()`。由于 1 在等宽字体中通常是一个较窄的字符，因此应用此修饰符会加宽所有 1 以及整个文本视图。文本视图中的非数字字符保持不变。

```swift
let myDate = DateComponents(
    calendar: Calendar(identifier: .gregorian),
    timeZone: TimeZone(identifier: "EST"),
    year: 2011,
    month: 1,
    day: 11,
    hour: 11,
    minute: 11
).date!

var body: some View {
    VStack(alignment: .leading) {
        Text(myDate.formatted(date: .long, time: .complete))
            .font(.system(size: 20))
        Text(myDate.formatted(date: .long, time: .complete))
            .font(.system(size: 20))
            .monospacedDigit()
    }
    .padding()
    .navigationTitle("monospacedDigit() Modifier")
}
```

如果文本视图的基础字体不支持等宽数字，则字体保持不变。

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

- **kerning(_:)**：设置字符间距（或字距调整）。

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/monospacedDigit()
crawled: 2025-12-01T02:39:20Z
---

# monospacedDigit()

**Instance Method**

Modifies the text view’s font to use fixed-width digits, while leaving other characters proportionally spaced.

## Declaration

```swift
nonisolated func monospacedDigit() -> Text
```

## Return Value

A text view with a modified font that uses fixed-width numeric characters, while leaving other characters proportionally spaced.

## Discussion

This modifier only affects numeric characters, and leaves all other characters unchanged.

The following example shows the effect of `monospacedDigit()` on a text view. It arranges two text views in a [VStack](../VStack.zh-Hans.md), each displaying a formatted date that contains many instances of the character 1. The second text view uses the `monospacedDigit()`. Because 1 is usually a narrow character in proportional fonts, applying the modifier widens all of the 1s, and the text view as a whole. The non-digit characters in the text view remain unaffected.

```swift
let myDate = DateComponents(
    calendar: Calendar(identifier: .gregorian),
    timeZone: TimeZone(identifier: "EST"),
    year: 2011,
    month: 1,
    day: 11,
    hour: 11,
    minute: 11
).date!

var body: some View {
    VStack(alignment: .leading) {
        Text(myDate.formatted(date: .long, time: .complete))
            .font(.system(size: 20))
        Text(myDate.formatted(date: .long, time: .complete))
            .font(.system(size: 20))
            .monospacedDigit()
    }
    .padding()
    .navigationTitle("monospacedDigit() Modifier")
}
```



If the base font of the text view doesn’t support fixed-width digits, the font remains unchanged.

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
- **kerning(_:)**: Sets the spacing, or kerning, between characters.
- **tracking(_:)**: Sets the tracking for the text.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

