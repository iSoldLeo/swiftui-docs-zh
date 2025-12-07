---

来源：https://developer.apple.com/documentation/SwiftUI/View/autocorrectionDisabled(_:)

抓取时间：2025-11-30T21:20:22Z

---

# autocorrectionDisabled(_:)

**实例方法**

设置是否禁用此视图的自动纠错功能。

## 声明

```swift
nonisolated func autocorrectionDisabled(_ disable: Bool = true) -> some View

```

## 参数

- **disable**：一个布尔值，指示是否禁用此视图的自动纠错功能。默认值为 `true`。

## 说明

当自动纠错功能会使用户难以输入信息时，请使用此方法。例如，输入专有名词和街道地址时，自动纠错功能可能会对用户完成数据输入任务的能力产生负面影响。

以下示例使用默认键盘配置 [TextField](../TextField.zh-Hans.md)。禁用自动更正功能后，用户可以输入任意文本，而不会受到自动更正系统的建议或覆盖。

```swift
TextField("1234 Main St.", text: $address)
    .keyboardType(.default)
    .autocorrectionDisabled(true)
```

## 管理文本输入

- **autocorrectionDisabled**：一个布尔值，用于确定视图层级是否启用自动更正。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 上为用户输入文本提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键自动启用的频率。

- **TextInputAutocapitalization**：文本输入时应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 watchOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义各平台上可用的系统文本格式控件的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/autocorrectionDisabled(_:)
crawled: 2025-11-30T21:20:22Z
---

# autocorrectionDisabled(_:)

**Instance Method**

Sets whether to disable autocorrection for this view.

## Declaration

```swift
nonisolated func autocorrectionDisabled(_ disable: Bool = true) -> some View

```

## Parameters

- **disable**: A Boolean value that indicates whether autocorrection is disabled for this view. The default value is `true`.

## Discussion

Use this method when the effect of autocorrection would make it more difficult for the user to input information. The entry of proper names and street addresses are examples where autocorrection can negatively affect the user’s ability complete a data entry task.

The example below configures a [TextField](../TextField.zh-Hans.md) with the default keyboard. Disabling autocorrection allows the user to enter arbitrary text without the autocorrection system offering suggestions or attempting to override their input.

```swift
TextField("1234 Main St.", text: $address)
    .keyboardType(.default)
    .autocorrectionDisabled(true)
```

## Managing text entry

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
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

