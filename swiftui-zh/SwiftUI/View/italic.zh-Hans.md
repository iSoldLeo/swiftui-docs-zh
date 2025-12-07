--- 来源：https://developer.apple.com/documentation/SwiftUI/View/italic(_:)

抓取时间：2025-12-02T17:34:52Z

---

# italic(_:)

**实例方法**

将文本设置为斜体。

## 声明

```swift
nonisolated func italic(_ isActive: Bool = true) -> some View

```

## 参数

- **isActive**：一个布尔值，指示是否添加斜体样式。默认值为 `true`。

## 返回值

一个带有斜体文本的视图。

## 控制文本样式

- **bold(_:)**：将文本设置为粗体。

- **underline(_:pattern:color:)**：为该视图中的文本添加下划线。

- **strikethrough(_:pattern:color:)**：为该视图中的文本添加删除线。

- **textCase(_:)**：设置该视图中文本显示时的大小写转换。

- **textCase**：使用环境语言设置，对 `Text` 进行样式覆盖，使其在显示时自动转换大小写。

- **monospaced(_:)**：尽可能将所有子视图的字体修改为使用当前字体的等宽变体。

- **monospacedDigit()**：尽可能将所有子视图的字体修改为使用等宽数字，同时保持其他字符按比例间距排列。

- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。

- **AttributedTextValueConstraint**：用于定义特定属性值约束的协议。

- **AttributedTextFormatting**：与属性文本格式定义相关的类型的命名空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/italic(_:)
crawled: 2025-12-02T17:34:52Z
---

# italic(_:)

**Instance Method**

Applies italics to the text in this view.

## Declaration

```swift
nonisolated func italic(_ isActive: Bool = true) -> some View

```

## Parameters

- **isActive**: A Boolean value that indicates whether italic styling is added. The default value is `true`.

## Return Value

A View with italic text.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

