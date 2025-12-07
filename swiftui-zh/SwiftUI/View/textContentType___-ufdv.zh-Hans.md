--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textContentType(_:)-ufdv

抓取时间：2025-12-02T17:35:25Z

---

# textContentType(_:)

**实例方法**

设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

## 声明

```swift
nonisolated func textContentType(_ textContentType: UITextContentType?) -> some View

```

## 参数

- **textContentType**：[doc://com.apple.documentation/documentation/UIKit/UITextContentType] 结构中可用的内容类型之一，用于标识文本输入区域预期的语义含义。这些类型包括电子邮件地址、位置名称、URL 和电话号码等等。

## 说明

使用此方法设置输入文本的内容类型。例如，您可以为电子邮件地址的输入配置 [TextField](../TextField.zh-Hans.md)：

```swift
TextField("Enter your email", text: $emailAddress)
    .textContentType(.emailAddress)
```

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层级是否启用自动更正。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互方式。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 用户输入文本时提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键自动启用的频率。

- **TextInputAutocapitalization**：文本输入时应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 watchOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 上为用户输入文本提供建议。

- **TextInputFormattingControlPlacement**：定义每个平台上可用的系统文本格式控件的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textContentType(_:)-ufdv
crawled: 2025-12-02T17:35:25Z
---

# textContentType(_:)

**Instance Method**

Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.

## Declaration

```swift
nonisolated func textContentType(_ textContentType: UITextContentType?) -> some View

```

## Parameters

- **textContentType**: One of the content types available in the [doc://com.apple.documentation/documentation/UIKit/UITextContentType] structure that identify the semantic meaning expected for a text-entry area. These include support for email addresses, location names, URLs, and telephone numbers, to name just a few.

## Discussion

Use this method to set the content type for input text. For example, you can configure a [TextField](../TextField.zh-Hans.md) for the entry of email addresses:

```swift
TextField("Enter your email", text: $emailAddress)
    .textContentType(.emailAddress)
```

## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
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
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

