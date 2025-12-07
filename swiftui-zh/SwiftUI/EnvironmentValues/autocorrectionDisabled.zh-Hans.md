---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/autocorrectionDisabled
抓取时间： 2025-12-02T17:35:16Z
---

# AutocorrectionDisabled

**实例属性**

布尔值，用于确定视图层次结构是否启用了自动更正功能。

## 声明

```swift
var autocorrectionDisabled: Bool { get set }
```

## 讨论

默认值为 `false`。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。
- **keyboardType(_:)**：设置此视图的键盘类型。
- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘交互的行为。
- **textContentType(_:)**：为该视图设置文本内容类型，当用户在 macOS 上输入文本时，系统会使用该类型提供建议。
- **textInputAutocapitalization(_:)**：设置键盘上的 shift 键自动启用的频率。
- **TextInputAutocapitalization**：在文本输入过程中应用的自动大写行为类型。
- **textInputCompletion(_:)**：在作为文本输入建议使用时，将一个完整的字符串与此视图的值相关联
- **textInputSuggestions(_:)**：配置此视图的文本输入建议。
- **textInputSuggestions(_:content:)**：配置该视图的文本输入建议：配置此视图的文本输入建议。
- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议：配置此视图的文本输入建议。
- **textContentType(_:)**：为该视图配置文本输入建议：为该视图设置文本内容类型，当用户在 watchOS 设备上输入文本时，系统会使用该类型提供建议。
- **textContentType(_:)**：为该视图设置文本内容类型，当用户在 macOS 上输入文本时，系统会使用该类型提供建议。
- **textContentType(_:)**：为该视图设置文本内容类型，当用户在 iOS 或 tvOS 设备上输入文本时，系统会使用该类型提供建议。
- **TextInputFormattingControlPlacement**：定义每个平台上可用的系统文本格式控件的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/autocorrectionDisabled
crawled: 2025-12-02T17:35:16Z
---

# autocorrectionDisabled

**Instance Property**

A Boolean value that determines whether the view hierarchy has auto-correction enabled.

## Declaration

```swift
var autocorrectionDisabled: Bool { get set }
```

## Discussion

The default value is `false`.

## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **keyboardType(_:)**: Sets the keyboard type for this view.
- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textInputAutocapitalization(_:)**: Sets how often the shift key in the keyboard is automatically enabled.
- **TextInputAutocapitalization**: The kind of autocapitalization behavior applied during text input.
- **textInputCompletion(_:)**: Associates a fully formed string with the value of this view when used as a text input suggestion
- **textInputSuggestions(_:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:content:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

