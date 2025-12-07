--- 来源：https://developer.apple.com/documentation/SwiftUI/TextInputAutocapitalization
抓取时间：2025-12-02T17:35:19Z

---

# TextInputAutocapitalization

**Structure**

文本输入时应用的自动大写行为类型。

## 声明

```swift
struct TextInputAutocapitalization
```

## 概述

将 `TextInputAutocapitalization` 的实例传递给 [textInputAutocapitalization(_:)](View/textInputAutocapitalization.zh-Hans.md) 视图修饰符。

## 获取自动大写选项

- **characters**：定义一种自动大写行为，该行为会将每个字母都大写。

- **sentences**：定义一种自动大写行为，该行为会将每个句子的首字母大写。

- **words**：定义自动大写行为，将每个单词的首字母大写。

- **never**：定义自动大写行为，不进行任何大写转换。

## 创建自动大写类型

- **init(_:)**：根据枚举类型 `UITextAutocapitalizationType` 创建一个新的 [TextInputAutocapitalization](TextInputAutocapitalization.zh-Hans.md) 结构体。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动纠错功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层次结构是否启用自动纠错功能。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 用户输入文本时提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键自动启用的频率。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 watchOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义各平台上可用的系统文本格式控件的结构。

## 符合以下标准

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/TextInputAutocapitalization
crawled: 2025-12-02T17:35:19Z
---

# TextInputAutocapitalization

**Structure**

The kind of autocapitalization behavior applied during text input.

## Declaration

```swift
struct TextInputAutocapitalization
```

## Overview

Pass an instance of `TextInputAutocapitalization` to the [textInputAutocapitalization(_:)](View/textInputAutocapitalization.zh-Hans.md) view modifier.

## Getting autocapitalization options

- **characters**: Defines an autocapitalizing behavior that will capitalize every letter.
- **sentences**: Defines an autocapitalizing behavior that will capitalize the first letter in every sentence.
- **words**: Defines an autocapitalizing behavior that will capitalize the first letter of every word.
- **never**: Defines an autocapitalizing behavior that will not capitalize anything.

## Creating an autocapitalization type

- **init(_:)**: Creates a new [TextInputAutocapitalization](TextInputAutocapitalization.zh-Hans.md) struct from a `UITextAutocapitalizationType` enum.

## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **keyboardType(_:)**: Sets the keyboard type for this view.
- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textInputAutocapitalization(_:)**: Sets how often the shift key in the keyboard is automatically enabled.
- **textInputCompletion(_:)**: Associates a fully formed string with the value of this view when used as a text input suggestion
- **textInputSuggestions(_:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:content:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

## Conforms To

- Sendable
- SendableMetatype

