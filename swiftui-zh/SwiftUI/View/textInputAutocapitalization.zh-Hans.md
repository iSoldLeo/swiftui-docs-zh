--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textInputAutocapitalization(_:)

抓取时间：2025-11-30T21:20:25Z

---

# textInputAutocapitalization(_:)

**实例方法**

设置键盘中 Shift 键自动启用的频率。

## 声明

```swift
nonisolated func textInputAutocapitalization(_ autocapitalization: TextInputAutocapitalization?) -> some View

```

## 参数

- **autocapitalization**：[TextInputAutocapitalization](../TextInputAutocapitalization.zh-Hans.md) 结构中定义的某种首字母大写行为，或 nil。

## 说明

当需要自动将单词、句子或其他文本（例如专有名词）的首字母大写时，请使用 `textInputAutocapitalization(_:)`。

在以下示例中，当用户输入文本时，Shift 键会在每个单词前自动启用：

```swift
TextField("Last, First", text: $fullName)
    .textInputAutocapitalization(.words)
```

[TextInputAutocapitalization](../TextInputAutocapitalization.zh-Hans.md) 结构体定义了可用的自动大写行为。向此视图修饰符提供 `nil` 不会更改自动大写行为。默认值为 `TextInputAutocapitalization.sentences`。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动纠错功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层次结构是否启用自动纠错。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 上为用户输入文本提供建议。

- **TextInputAutocapitalization**：文本输入期间应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 watchOS 设备上为用户输入文本提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义各平台上可用的系统文本格式控件的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textInputAutocapitalization(_:)
crawled: 2025-11-30T21:20:25Z
---

# textInputAutocapitalization(_:)

**Instance Method**

Sets how often the shift key in the keyboard is automatically enabled.

## Declaration

```swift
nonisolated func textInputAutocapitalization(_ autocapitalization: TextInputAutocapitalization?) -> some View

```

## Parameters

- **autocapitalization**: One of the capitalizing behaviors defined in the [TextInputAutocapitalization](../TextInputAutocapitalization.zh-Hans.md) struct or nil.

## Discussion

Use `textInputAutocapitalization(_:)` when you need to automatically capitalize words, sentences, or other text like proper nouns.

In example below, as the user enters text the shift key is automatically enabled before every word:

```swift
TextField("Last, First", text: $fullName)
    .textInputAutocapitalization(.words)
```

The [TextInputAutocapitalization](../TextInputAutocapitalization.zh-Hans.md) struct defines the available autocapitalizing behavior. Providing `nil` to  this view modifier does not change the autocapitalization behavior. The default is `TextInputAutocapitalization.sentences`.

## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **keyboardType(_:)**: Sets the keyboard type for this view.
- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **TextInputAutocapitalization**: The kind of autocapitalization behavior applied during text input.
- **textInputCompletion(_:)**: Associates a fully formed string with the value of this view when used as a text input suggestion
- **textInputSuggestions(_:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:content:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

