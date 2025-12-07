--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/monospacedDigit()

抓取时间：2025-12-03T06:18:07Z

---

# monospacedDigit()

**实例方法**

返回一个修改后的字体，该字体使用等宽数字，而其他字符保持等宽。

## 声明

```swift
func monospacedDigit() -> Font
```

## 返回值

一个使用等宽数字字符的字体。

## 说明

此修改器仅影响数字字符，其他字符保持不变。如果基础字体不支持等宽数字或等宽数字，则字体保持不变。

以下示例显示了两个文本字段以 [VStack](../VStack.zh-Hans.md) 排列。两个文本字段都指定了 12 磅的系统字体，第二个文本字段在字体上添加了 `monospacedDigit()` 修饰符。由于文本中包含数字 1（在比例字体中通常是一个窄字符），因此第二个文本字段的宽度会比第一个文本字段更宽。

```swift
@State private var userText = "Effect of monospacing digits: 111,111."

var body: some View {
    VStack {
        TextField("Proportional", text: $userText)
            .font(.system(size: 12))
        TextField("Monospaced", text: $userText)
            .font(.system(size: 12).monospacedDigit())
    }
    .padding()
    .navigationTitle(Text("Font + monospacedDigit()"))
}
```

## 字体样式

- **bold()**：为字体添加粗体或强调样式。

- **italic()**：为字体添加斜体。

- **monospaced()**：返回与基础字体同一字体系列的等宽字体。

- **smallCaps()**：调整字体以启用所有小型大写字母。

- **lowercaseSmallCaps()**：调整字体以启用小写小型大写字母。

- **uppercaseSmallCaps()**：调整字体以启用小写字母大写。

- **weight(_:)**：设置字体粗细。

- **width(_:)**：设置字体宽度。

- **Font.Width**：用于具有多种宽度的字体。

- **leading(_:)**：调整字体的行距。

- **Font.Leading**：可应用于字体的行距调整。


---
source: https://developer.apple.com/documentation/SwiftUI/Font/monospacedDigit()
crawled: 2025-12-03T06:18:07Z
---

# monospacedDigit()

**Instance Method**

Returns a modified font that uses fixed-width digits, while leaving other characters proportionally spaced.

## Declaration

```swift
func monospacedDigit() -> Font
```

## Return Value

A font that uses fixed-width numeric characters.

## Discussion

This modifier only affects numeric characters, and leaves all other characters unchanged. If the base font doesn’t support fixed-width, or *monospace* digits, the font remains unchanged.

The following example shows two text fields arranged in a [VStack](../VStack.zh-Hans.md). Both text fields specify the 12-point system font, with the second adding the `monospacedDigit()` modifier to the font. Because the text includes the digit 1, normally a narrow character in proportional fonts, the second text field becomes wider than the first.

```swift
@State private var userText = "Effect of monospacing digits: 111,111."

var body: some View {
    VStack {
        TextField("Proportional", text: $userText)
            .font(.system(size: 12))
        TextField("Monospaced", text: $userText)
            .font(.system(size: 12).monospacedDigit())
    }
    .padding()
    .navigationTitle(Text("Font + monospacedDigit()"))
}
```



## Styling a font

- **bold()**: Adds bold or emphasized styling to the font.
- **italic()**: Adds italics to the font.
- **monospaced()**: Returns a fixed-width font from the same family as the base font.
- **smallCaps()**: Adjusts the font to enable all small capitals.
- **lowercaseSmallCaps()**: Adjusts the font to enable lowercase small capitals.
- **uppercaseSmallCaps()**: Adjusts the font to enable uppercase small capitals.
- **weight(_:)**: Sets the weight of the font.
- **width(_:)**: Sets the width of the font.
- **Font.Width**: A width to use for fonts that have multiple widths.
- **leading(_:)**: Adjusts the line spacing of a font.
- **Font.Leading**: A line spacing adjustment that you can apply to a font.

