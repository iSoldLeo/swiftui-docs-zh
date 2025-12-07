---
来源： https://developer.apple.com/documentation/swiftui/attributedtextformatting
抓取时间： 2025-12-05T22:23:30Z
---

# 属性文本格式

**Enumeration**

属性文本格式定义相关类型的命名空间。

## 声明

```swift
enum AttributedTextFormatting
```

## 概览



## 结构

- **AttributedTextFormatting.AnyDefinition**：类型擦除的文本格式定义。
- **AttributedTextFormatting.AttributeContainerProxy**：部分已验证属性集的代理。
- **AttributedTextFormatting.DefinitionBuilder**：属性文本格式定义的结果生成器。
- **AttributedTextFormatting.EmptyDefinition**：对属性值无限制的文本格式定义。
- **AttributedTextFormatting.Transferable**：在 SwiftUI 环境中解释的属性字符串的可转移表示。
- **AttributedTextFormatting.TupleDefinition**：文本格式定义，用于执行一系列文本格式定义的约束。
- **AttributedTextFormatting.ValueConstraint**：文本格式定义，用于将单个属性的值约束为集合的成员。

## 控制文本样式

- **bold(_:)**：为该视图中的文本应用粗体字体权重。
- **italic(_:)**：为该视图中的文本应用斜体。
- **underline(_:pattern:color:)**：为该视图中的文本添加下划线。
- **strikethrough(_:pattern:color:)**：为该视图中的文本应用删除线。
- **textCase(_:)**：为该视图中包含的文本在显示时的大小写设置变换。
- **textCase**：样式覆盖，用于在显示`Text` 时使用环境的本地语言转换大小写。
- **monospaced(_:)**：尽可能修改所有子视图的字体，使其使用当前字体的固定宽度变体。
- **monospacedDigit()**：修改所有子视图的字体，尽可能使用固定宽度的数字，同时按比例保留其他字符的间距。
- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。
- **AttributedTextValueConstraint**：用于定义对特定属性值的约束的协议。


---
source: https://developer.apple.com/documentation/swiftui/attributedtextformatting
crawled: 2025-12-05T22:23:30Z
---

# AttributedTextFormatting

**Enumeration**

A namespace for types related to attributed text formatting definitions.

## Declaration

```swift
enum AttributedTextFormatting
```

## Overview



## Structures

- **AttributedTextFormatting.AnyDefinition**: A type-erased text formatting definition.
- **AttributedTextFormatting.AttributeContainerProxy**: A proxy for a partially validated set of attributes.
- **AttributedTextFormatting.DefinitionBuilder**: A result builder for attributed text formatting definition.
- **AttributedTextFormatting.EmptyDefinition**: A text formatting definition that places no constraints on the values of attributes.
- **AttributedTextFormatting.Transferable**: A transferable representation of an attributed string interpreted in a SwiftUI environment.
- **AttributedTextFormatting.TupleDefinition**: A text formatting definition that enforces the constraints of a series of text formatting definitions.
- **AttributedTextFormatting.ValueConstraint**: A text formatting definition that constrains the value of a single attribute to the members of a set.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.

