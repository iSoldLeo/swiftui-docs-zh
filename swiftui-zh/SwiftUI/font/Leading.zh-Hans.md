--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/leading(_:)

抓取时间：2025-12-03T06:18:12Z

---

# leading(_:)

**实例方法**

调整字体的行间距。

## 声明

```swift
func leading(_ leading: Font.Leading) -> Font
```

## 参数

- **leading**：要应用的行间距调整值。

## 返回值

使用指定行间距的修改后的字体；如果原始字体不支持行间距调整，则返回原始字体。

## 说明

通过应用此修饰符，您可以在保持字体其他特性不变的情况下更改字体的行间距。例如，您可以通过将 [tight](Leading/tight.zh-Hans.md) 值应用于 [body](body.zh-Hans.md) 字体来减小其间距：

```swift
let myFont = Font.body.leading(.tight)
```

行距调整的可用性取决于字体。对于某些字体，此修饰符无效，并返回原始字体。

## 字体样式

- **bold()**：为字体添加粗体或强调样式。

- **italic()**：为字体添加斜体。

- **monospaced()**：返回与基础字体属于同一字体系列的等宽字体。

- **monospacedDigit()**：返回一个修改后的字体，该字体使用等宽数字，而其他字符保持比例间距。

- **smallCaps()**：调整字体以启用所有小型大写字母。

- **lowercaseSmallCaps()**：调整字体以启用小型小写字母。

- **uppercaseSmallCaps()**：调整字体以启用小型大写字母。

- **weight(_:)**：设置字体粗细。

- **width(_:)**：设置字体宽度。

- **Font.Width**：用于具有多种宽度的字体的宽度设置。

- **Font.Leading**：可应用于字体的行距调整。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/leading(_:)
crawled: 2025-12-03T06:18:12Z
---

# leading(_:)

**Instance Method**

Adjusts the line spacing of a font.

## Declaration

```swift
func leading(_ leading: Font.Leading) -> Font
```

## Parameters

- **leading**: The line spacing adjustment to apply.

## Return Value

A modified font that uses the specified line spacing, or the original font if it doesn’t support line spacing adjustments.

## Discussion

You can change a font’s line spacing while maintaining other characteristics of the font by applying this modifier. For example, you can decrease spacing of the [body](body.zh-Hans.md) font by applying the [tight](Leading/tight.zh-Hans.md) value to it:

```swift
let myFont = Font.body.leading(.tight)
```

The availability of leading adjustments depends on the font. For some fonts, the modifier has no effect and returns the original font.

## Styling a font

- **bold()**: Adds bold or emphasized styling to the font.
- **italic()**: Adds italics to the font.
- **monospaced()**: Returns a fixed-width font from the same family as the base font.
- **monospacedDigit()**: Returns a modified font that uses fixed-width digits, while leaving other characters proportionally spaced.
- **smallCaps()**: Adjusts the font to enable all small capitals.
- **lowercaseSmallCaps()**: Adjusts the font to enable lowercase small capitals.
- **uppercaseSmallCaps()**: Adjusts the font to enable uppercase small capitals.
- **weight(_:)**: Sets the weight of the font.
- **width(_:)**: Sets the width of the font.
- **Font.Width**: A width to use for fonts that have multiple widths.
- **Font.Leading**: A line spacing adjustment that you can apply to a font.

