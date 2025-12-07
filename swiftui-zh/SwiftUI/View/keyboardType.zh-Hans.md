--- 来源：https://developer.apple.com/documentation/SwiftUI/View/keyboardType(_:)

抓取时间：2025-12-02T17:35:17Z

---

# keyboardType(_:)

**实例方法**

设置此视图的键盘类型。

## 声明

```swift
nonisolated func keyboardType(_ type: UIKeyboardType) -> some View

```

## 参数

- **type**：枚举 [doc://com.apple.documentation/documentation/UIKit/UIKeyboardType] 中定义的键盘类型之一。

## 说明

使用 `keyboardType(_:)` 指定用于文本输入的键盘类型。有多种不同的键盘类型可供选择，以满足特定的输入需求，例如输入电子邮件地址或电话号码。

以下示例演示了如何使用 [TextField](../TextField.zh-Hans.md) 输入电子邮件地址。将文本字段的键盘类型设置为 `.emailAddress` 可确保用户只能输入格式正确的电子邮件地址。

```swift
TextField("someone@example.com", text: $emailAddress)
    .keyboardType(.emailAddress)
```

[doc://com.apple.documentation/documentation/UIKit/UIKeyboardType] 枚举中提供了几种不同的专用键盘类型。要指定默认系统键盘类型，请使用 `.default`。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层次结构是否启用自动更正。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 用户输入文本时提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键的自动启用频率。

- **TextInputAutocapitalization**：文本输入期间应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 watchOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义各平台上可用的系统文本格式控件的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/View/keyboardType(_:)
crawled: 2025-12-02T17:35:17Z
---

# keyboardType(_:)

**Instance Method**

Sets the keyboard type for this view.

## Declaration

```swift
nonisolated func keyboardType(_ type: UIKeyboardType) -> some View

```

## Parameters

- **type**: One of the keyboard types defined in the [doc://com.apple.documentation/documentation/UIKit/UIKeyboardType] enumeration.

## Discussion

Use `keyboardType(_:)` to specify the keyboard type to use for text entry. A number of different keyboard types are available to meet specialized input needs, such as entering email addresses or phone numbers.

The example below presents a [TextField](../TextField.zh-Hans.md) to input an email address. Setting the text field’s keyboard type to `.emailAddress` ensures the user can only enter correctly formatted email addresses.

```swift
TextField("someone@example.com", text: $emailAddress)
    .keyboardType(.emailAddress)
```

There are several different kinds of specialized keyboard types available though the [doc://com.apple.documentation/documentation/UIKit/UIKeyboardType] enumeration. To specify the default system keyboard type, use `.default`.



## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
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

