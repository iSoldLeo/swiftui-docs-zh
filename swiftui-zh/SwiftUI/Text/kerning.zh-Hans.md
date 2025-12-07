--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/kerning(_:)

抓取时间：2025-12-02T21:48:30Z

---

# kerning(_:)

**实例方法**

设置字符之间的间距，即字距调整。

## 声明

```swift
nonisolated func kerning(_ kerning: CGFloat) -> Text
```

## 参数

- **kerning**：此文本中各个字符之间的间距。值为 `0` 时，字距调整将设置为系统默认值。

## 返回值

应用指定字距调整后的文本。

## 说明

字距调整定义了文本视图中字符相对于默认间距的偏移量（以磅为单位）。使用正字距调整值可以增大字符之间的间距。使用负字距调整值可以缩小字符之间的间距。

```swift
VStack(alignment: .leading) {
    Text("ABCDEF").kerning(-3)
    Text("ABCDEF")
    Text("ABCDEF").kerning(3)
}
```

第一个例子中的最后一个字符使用了负字距调整，由于字距调整也会影响文本视图的后缘，因此会出现裁剪。

字距调整旨在保持连字。例如，Hoefler Text 字体使用连字 *ffl*，如单词 *raffle* 中的字母组合，此处分别展示了略微负字距调整和略微正字距调整的效果：

当其他字母靠近或远离时，字母组合 *ffl* 的形状保持不变。但是，当字距调整超过某个特定值时，非必要的连字就会失效。

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

- **tracking(_:)**：设置文本的字距。

- **baselineOffset(_:)**：设置文本相对于基线的垂直偏移量。

- **Text.Case**：用于转换文本中字符大小写的方案。

- **Text.DateStyle**：用于显示 `Date` 的预定义样式。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/kerning(_:)
crawled: 2025-12-02T21:48:30Z
---

# kerning(_:)

**Instance Method**

Sets the spacing, or kerning, between characters.

## Declaration

```swift
nonisolated func kerning(_ kerning: CGFloat) -> Text
```

## Parameters

- **kerning**: The spacing to use between individual characters in this text. Value of `0` sets the kerning to the system default value.

## Return Value

Text with the specified amount of kerning.

## Discussion

Kerning defines the offset, in points, that a text view should shift characters from the default spacing. Use positive kerning to widen the spacing between characters. Use negative kerning to tighten the spacing between characters.

```swift
VStack(alignment: .leading) {
    Text("ABCDEF").kerning(-3)
    Text("ABCDEF")
    Text("ABCDEF").kerning(3)
}
```

The last character in the first case, which uses negative kerning, experiences cropping because the kerning affects the trailing edge of the text view as well.



Kerning attempts to maintain ligatures. For example, the Hoefler Text font uses a ligature for the letter combination *ffl*, as in the word *raffle*, shown here with a small negative and a small positive kerning:



The *ffl* letter combination keeps a constant shape as the other letters move together or apart. Beyond a certain point in either direction, however, kerning does disable nonessential ligatures.





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
- **tracking(_:)**: Sets the tracking for the text.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline.
- **Text.Case**: A scheme for transforming the capitalization of characters within text.
- **Text.DateStyle**: A predefined style used to display a `Date`.

