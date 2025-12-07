--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textCase(_:)

抓取时间：2025-11-30T21:20:01Z

---

# textCase(_:)

**实例方法**

设置此视图中文本显示时的大小写转换。

## 声明

```swift
nonisolated func textCase(_ textCase: Text.Case?) -> some View

```

## 参数

- **textCase**：[Case](../Text/Case.zh-Hans.md) 枚举值之一；默认值为 `nil`。

## 返回值

一个转换文本大小写的视图。

## 说明

默认值为 `nil`，表示文本不进行任何大小写更改。

## 控制文本样式

- **bold(_:)**：将本视图中的文本设置为粗体。

- **italic(_:)**：将本视图中的文本设置为斜体。

- **underline(_:pattern:color:)**：将本视图中的文本设置为下划线。

- **strikethrough(_:pattern:color:)**：将本视图中的文本设置为删除线。

- **textCase**：使用环境语言设置，在显示时更改 `Text` 的大小写。

- **monospaced(_:)**：尽可能将所有子视图的字体设置为当前字体的等宽字体。

- **monospacedDigit()**：尽可能将所有子视图的字体设置为等宽数字，同时保持其他字符按比例间距排列。

- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。

- **AttributedTextValueConstraint**：用于定义特定属性值约束的协议。

- **AttributedTextFormatting**：与属性文本格式定义相关的类型的命名空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textCase(_:)
crawled: 2025-11-30T21:20:01Z
---

# textCase(_:)

**Instance Method**

Sets a transform for the case of the text contained in this view when displayed.

## Declaration

```swift
nonisolated func textCase(_ textCase: Text.Case?) -> some View

```

## Parameters

- **textCase**: One of the [Case](../Text/Case.zh-Hans.md) enumerations; the default is `nil`.

## Return Value

A view that transforms the case of the text.

## Discussion

The default value is `nil`, displaying the text without any case changes.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

