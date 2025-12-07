--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textInputSuggestions(_:content:)

抓取时间：2025-11-30T21:20:28Z

---

# textInputSuggestions(_:content:)

**实例方法**

配置此视图的文本输入建议。

## 声明

```swift
nonisolated func textInputSuggestions<Data, Content>(_ data: Data, @ViewBuilder content: @escaping (Data.Element) -> Content) -> some View where Data : RandomAccessCollection, Content : View, Data.Element : Identifiable

```

## 参数

- **data**：用于动态创建视图的数据。

- **content**：用于动态创建视图的视图构建器。

## 说明

您可以通过向此修饰符提供数据，在文本输入操作期间提供文本补全建议。当用户激活文本编辑界面时，界面会将建议视图显示为选项列表。

通过将 [textInputCompletion(_:)](textInputCompletion.zh-Hans.md) 修饰符添加到视图，即可将字符串与每个建议视图关联起来。

使用 `Label` 获取带有图像的平台标准建议文本可视化表示，使用 `Section` 获取带有标签的结果部分。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层次结构是否启用自动更正功能。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 macOS 上用户输入文本时提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键的自动启用频率。

- **TextInputAutocapitalization**：文本输入期间应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在 watchOS 设备上用户输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义各平台上可用的系统文本格式控件的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textInputSuggestions(_:content:)
crawled: 2025-11-30T21:20:28Z
---

# textInputSuggestions(_:content:)

**Instance Method**

Configures the text input suggestions for this view.

## Declaration

```swift
nonisolated func textInputSuggestions<Data, Content>(_ data: Data, @ViewBuilder content: @escaping (Data.Element) -> Content) -> some View where Data : RandomAccessCollection, Content : View, Data.Element : Identifiable

```

## Parameters

- **data**: The data that is used to create views dynamically.
- **content**: The view builder that creates views dynamically.

## Discussion

You can suggest text completions during a text input operation by providing data to this modifier. The interface presents the suggestion views as a list of choices when someone activates the text editing interface.

Associate a string with each suggestion view by adding the [textInputCompletion(_:)](textInputCompletion.zh-Hans.md) modifier to the view.

Use `Label` to get platform-standard visual representations of suggestion text accompanied with images, and `Section` for labelled sections of results.

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
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

