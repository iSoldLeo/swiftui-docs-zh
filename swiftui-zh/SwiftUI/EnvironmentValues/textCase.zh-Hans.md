---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/textCase
抓取时间： 2025-12-02T17:34:55Z
---

# textCase

**实例属性**

样式覆盖，用于在显示`Text` 时，使用环境的本地语言转换大小写。

### 声明

```swift
var textCase: Text.Case? { get set }
```

## 讨论

默认值为 `nil`，显示 `Text`，不改变任何大小写。

## 控制文本样式

- **bold(_:)**：为该视图中的文本添加粗体字。
- **italic(_:)**：为该视图中的文本应用斜体。
- **underline(_:pattern:color:)**：为该视图中的文本添加下划线。
- **strikethrough(_:pattern:color:)**：为该视图中的文本应用删除线。
- **textCase(_:)**：为该视图中包含的文本在显示时的大小写设置变换。
- **monospaced(_:)**：尽可能修改所有子视图的字体，使其使用当前字体的固定宽度变体。
- **monospacedDigit()**：修改所有子视图的字体，尽可能使用固定宽度的数字，同时按比例保留其他字符的间距。
- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。
- **AttributedTextValueConstraint**：用于定义某个属性值的约束的协议。
- **AttributedTextFormatting**：与归属文本格式定义相关的类型命名空间。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/textCase
crawled: 2025-12-02T17:34:55Z
---

# textCase

**Instance Property**

A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.

## Declaration

```swift
var textCase: Text.Case? { get set }
```

## Discussion

The default value is `nil`, displaying the `Text` without any case changes.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

