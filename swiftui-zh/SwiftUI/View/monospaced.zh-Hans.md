--- 来源：https://developer.apple.com/documentation/SwiftUI/View/monospaced(_:)

抓取时间：2025-12-02T17:34:55Z

---

# monospaced(_:)

**实例方法**

尽可能将所有子视图的字体修改为当前字体的等宽版本。

## 声明

```swift
nonisolated func monospaced(_ isActive: Bool = true) -> some View

```

## 返回值

返回一个视图，该视图的子视图字体使用等宽字符，而其他字符保持等宽。

## 说明

如果子视图的基础字体不支持等宽，则字体保持不变。

## 控制文本样式

- **bold(_:)**：为该视图中的文本应用粗体。

- **italic(_:)**：为该视图中的文本应用斜体。

- **underline(_:pattern:color:)**：为该视图中的文本应用下划线。

- **strikethrough(_:pattern:color:)**：为该视图中的文本应用删除线。

- **textCase(_:)**：设置该视图中文本显示时的大小写转换。

- **textCase**：使用环境语言设置，覆盖 `Text` 的样式，使其在显示时自动转换大小写。

- **monospacedDigit()**：修改所有子视图的字体，尽可能使用等宽数字，同时保持其他字符按比例间距排列。

- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。

- **AttributedTextValueConstraint**：用于定义特定属性值约束的协议。

- **AttributedTextFormatting**：与属性文本格式定义相关的类型的命名空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/monospaced(_:)
crawled: 2025-12-02T17:34:55Z
---

# monospaced(_:)

**Instance Method**

Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.

## Declaration

```swift
nonisolated func monospaced(_ isActive: Bool = true) -> some View

```

## Return Value

A view whose child views’ fonts use fixed-width characters, while leaving other characters proportionally spaced.

## Discussion

If a child view’s base font doesn’t support fixed-width, the font remains unchanged.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

