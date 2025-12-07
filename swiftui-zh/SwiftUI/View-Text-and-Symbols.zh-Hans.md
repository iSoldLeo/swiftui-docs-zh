---
来源： https://developer.apple.com/documentation/SwiftUI/View-Text-and-Symbols
抓取时间： 2025-12-02T17:22:10Z
---

# 文本和符号修饰符

**API 集合**

管理视图中文本的渲染、选择和输入。

### 概览

SwiftUI 提供了向用户显示文本的内置视图（如 [Text](Text.zh-Hans.md) 和 [Label](Label.zh-Hans.md)），或收集用户文本的视图（如 [TextField](TextField.zh-Hans.md) 和 [TextEditor](TextEditor.zh-Hans.md)）。使用文本和符号修改器可控制 SwiftUI 显示和管理文本的方式。例如，您可以设置字体、指定文本布局参数，以及指明期望的输入类型。

要进一步了解用于显示文本的视图类型以及配置这些视图的方法，请参阅[Text-input-and-output](Text-input-and-output.zh-Hans.md)。

## 字体

- **font(_:)**：设置此视图中文本的默认字体。

## 动态类型

- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。

### 文本样式

- **bold(_:)**：为该视图中的文本应用粗体字。
- **fontDesign(_:)**：设置此视图中文本的字体设计。
- **fontWeight(_:)**：设置此视图中文本的字体重量。
- **fontWidth(_:)**：设置此视图中文本的字体宽度。
- **italic(_:)**：为该视图中的文本应用斜体。
- **monospaced(_:)**：尽可能修改所有子视图的字体，使其使用当前字体的固定宽度变体。
- **monospacedDigit()**：修改所有子视图的字体，尽可能使用固定宽度的数字，同时按比例保留其他字符的间距。
- **strikethrough(_:pattern:color:)**：为该视图中的文本添加删除线。
- **textCase(_:)**：为该视图中包含的文本在显示时的大小写设置变换。
- **textScale(_:isEnabled:)**：为视图中的文本应用文本缩放比例。
- **underline(_:pattern:color:)**：为该视图中的文本应用下划线。

## 文本布局

- **allowsTightening(_:)**：设置该视图中的文本是否可以在必要时压缩字符之间的空格，以适应一行中的文本。
- **baselineOffset(_:)**：设置该视图中文本相对于基线的垂直偏移。
- **flipsForRightToLeftLayoutDirection(_:)**：设置当布局方向为从右到左时，此视图是否水平镜像其内容。
- **kerning(_:)**：设置该视图中文本的字符间距或字间距。
- **minimumScaleFactor(_:)**：设置该视图中的文本缩小以适应可用空间的最小量。
- **tracking(_:)**：设置此视图中文本的跟踪。
- **truncationMode(_:)**：为过长的文本行设置截断模式，以适应可用空间。
- **typesettingLanguage(_:isEnabled:)**：指定排版语言。

## 多行文本

- **lineLimit(_:)**：将此视图中文本可占的行数设置为一个封闭范围。
- **lineLimit(_:reservesSpace:)**：设置此视图中文本可占行数的限制。
- **lineSpacing(_:)**：设置此视图中文本行间的空间大小。
- **multilineTextAlignment(_:)**：设置包含多行文本的文本视图的对齐方式。

## 文本选择

- **textSelection(_:)**：控制是否可以在该视图中选择文本。

## 文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。
- **keyboardType(_:)**：设置此视图的键盘类型。
- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘交互的行为。
- **textInputAutocapitalization(_:)**：设置自动启用键盘中 shift 键的频率。
- **textInputCompletion(_:)**：当作为文本输入建议使用时，将一个完整的字符串与此视图的值相关联
- **textInputSuggestions(_:)**：配置此视图的文本输入建议。
- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。
- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议：配置此视图的文本输入建议。
- **textContentType(_:)**：为该视图设置文本内容类型，当用户在 watchOS 设备上输入文本时，系统会使用该类型提供建议。
- **textContentType(_:)**：为该视图设置文本内容类型，当用户在 macOS 上输入文本时，系统会使用该类型提供建议。
- **textContentType(_:)**：为该视图设置文本内容类型，当用户在 iOS 或 tvOS 设备上输入文本时，系统会使用该类型提供建议。

## 查找和替换

- **findNavigator(isPresented:)**：以编程方式为文本编辑器视图显示查找和替换界面。
- **findDisabled(_:)**：防止在文本编辑器中进行查找和替换操作。
- **replaceDisabled(_:)**：防止在文本编辑器中进行查找和替换操作：防止在文本编辑器中进行替换操作。

## 符号外观

- **symbolRenderingMode(_:)**：设置该视图中符号图像的渲染模式。
- **symbolVariant(_:)**：使视图中的符号显示特定变体。

## 配置视图元素

- **可访问性修改器**：让每个人（包括残障人士）都能访问您的 SwiftUI 应用程序。
- 外观修改器***：配置视图的前景和背景样式、控件和可见性。
- 辅助视图修改器**：添加和配置辅助视图，如工具栏和上下文菜单。
- **图表视图修改器**：配置使用 Swift 图表声明的图表。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Text-and-Symbols
crawled: 2025-12-02T17:22:10Z
---

# Text and symbol modifiers

**API Collection**

Manage the rendering, selection, and entry of text in your view.

## Overview

SwiftUI provides built-in views that display text to the user, like [Text](Text.zh-Hans.md) and [Label](Label.zh-Hans.md), or that collect text from the user, like [TextField](TextField.zh-Hans.md) and [TextEditor](TextEditor.zh-Hans.md). Use text and symbol modifiers to control how SwiftUI displays and manages that text. For example, you can set a font, specify text layout parameters, and indicate what kind of input to expect.

To learn more about the kinds of views that you use to display text and the ways in which you can configure those views, see [Text-input-and-output](Text-input-and-output.zh-Hans.md).

## Fonts

- **font(_:)**: Sets the default font for text in this view.

## Dynamic type

- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.

## Text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **fontDesign(_:)**: Sets the font design of the text in this view.
- **fontWeight(_:)**: Sets the font weight of the text in this view.
- **fontWidth(_:)**: Sets the font width of the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.

## Text layout

- **allowsTightening(_:)**: Sets whether text in this view can compress the space between characters when necessary to fit text in a line.
- **baselineOffset(_:)**: Sets the vertical offset for the text relative to its baseline in this view.
- **flipsForRightToLeftLayoutDirection(_:)**: Sets whether this view mirrors its contents horizontally when the layout direction is right-to-left.
- **kerning(_:)**: Sets the spacing, or kerning, between characters for the text in this view.
- **minimumScaleFactor(_:)**: Sets the minimum amount that text in this view scales down to fit in the available space.
- **tracking(_:)**: Sets the tracking for the text in this view.
- **truncationMode(_:)**: Sets the truncation mode for lines of text that are too long to fit in the available space.
- **typesettingLanguage(_:isEnabled:)**: Specifies the language for typesetting.

## Multiline text

- **lineLimit(_:)**: Sets to a closed range the number of lines that text can occupy in this view.
- **lineLimit(_:reservesSpace:)**: Sets a limit for the number of lines text can occupy in this view.
- **lineSpacing(_:)**: Sets the amount of space between lines of text in this view.
- **multilineTextAlignment(_:)**: Sets the alignment of a text view that contains multiple lines of text.

## Text selection

- **textSelection(_:)**: Controls whether people can select text within this view.

## Text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **keyboardType(_:)**: Sets the keyboard type for this view.
- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **textInputAutocapitalization(_:)**: Sets how often the shift key in the keyboard is automatically enabled.
- **textInputCompletion(_:)**: Associates a fully formed string with the value of this view when used as a text input suggestion
- **textInputSuggestions(_:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:content:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.

## Find and replace

- **findNavigator(isPresented:)**: Programmatically presents the find and replace interface for text editor views.
- **findDisabled(_:)**: Prevents find and replace operations in a text editor.
- **replaceDisabled(_:)**: Prevents replace operations in a text editor.

## Symbol appearance

- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **symbolVariant(_:)**: Makes symbols within the view show a particular variant.

## Configuring view elements

- **Accessibility modifiers**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Appearance modifiers**: Configure a view’s foreground and background styles, controls, and visibility.
- **Auxiliary view modifiers**: Add and configure supporting views, like toolbars and context menus.
- **Chart view modifiers**: Configure charts that you declare with Swift Charts.

