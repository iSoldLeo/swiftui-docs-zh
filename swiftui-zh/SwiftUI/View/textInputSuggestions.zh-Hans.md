---

来源：https://developer.apple.com/documentation/SwiftUI/View/textInputSuggestions(_:)

抓取时间：2025-12-02T17:35:21Z

---

# textInputSuggestions(_:)

**实例方法**

配置此视图的文本输入建议。

## 声明

```swift
nonisolated func textInputSuggestions<S>(@ViewBuilder _ suggestions: () -> S) -> some View where S : View

```

## 参数

- **suggestions**：一个视图构建器，用于生成填充建议列表的内容。

## 说明

您可以通过向此修饰符提供视图集合，在文本输入操作期间提供文本补全建议。当用户激活文本编辑界面时，界面会将建议视图显示为选项列表。

通过向视图添加 [textInputCompletion(_:)](textInputCompletion.zh-Hans.md) 修饰符，将字符串与每个建议视图关联起来。

使用 `Label` 获取带有图片的平台标准建议文本可视化表示，使用 `Section` 获取带有标签的结果部分。

例如，您可以通过显示场所名称来建议地址，并在每个情况下提供相应的地址作为文本补全：

```swift
TextField("Location", text: $addressText)
    .textInputSuggestions {
        Text("The Fillmore")
            .textInputCompletion("1805 Geary Blvd, San Francisco")
        Text("The Catalyst")
            .textInputCompletion("1011 Pacific Ave, Santa Cruz")
        Text("Rio Theatre")
            .textInputCompletion("1205 Soquel Ave, Santa Cruz")
    }
```

当用户选择建议时，SwiftUI 会将文本字段中的文本替换为文本补全字符串。如果您省略特定建议视图的文本补全修饰符，SwiftUI 将显示该建议，但该建议视图不会响应点击或单击操作。

您可以根据条件的变化更新提供的建议。

例如，您可以指定一个存储在模型中的建议数组：

```swift
TextField("Location", text: $addressText)
    .textInputSuggestions {
        ForEach(model.suggestedVenues) { venue in
            Label(venue.name, image: venue.image)
                .textInputCompletion(venue.address)
        }
    }
```

如果模型的 `suggestedVenues` 初始为空数组，则界面最初不会显示任何建议。然后，您可以提供逻辑，根据某些条件更新数组。例如，您可以根据当前文本更新补全建议。请注意，某些事件或操作（例如用户移动 macOS 窗口）可能会关闭建议视图。

## 管理文本输入

- **autocorrectionDisabled(_:)**：设置是否禁用此视图的自动更正功能。

- **autocorrectionDisabled**：一个布尔值，用于确定视图层级结构是否启用自动更正。

- **keyboardType(_:)**：设置此视图的键盘类型。

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 上输入文本时提供建议。

- **textInputAutocapitalization(_:)**：设置键盘中 Shift 键自动启用的频率。

- **TextInputAutocapitalization**：文本输入时应用的自动大写行为类型。

- **textInputCompletion(_:)**：将一个完整的字符串与此视图的值关联起来，以便用作文本输入建议。

- **textInputSuggestions(_:content:)**：配置此视图的文本输入建议。

- **textInputSuggestions(_:id:content:)**：配置此视图的文本输入建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 watchOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 macOS 设备上输入文本时提供建议。

- **textContentType(_:)**：设置此视图的文本内容类型，系统会使用此类型在用户于 iOS 或 tvOS 设备上输入文本时提供建议。

- **TextInputFormattingControlPlacement**：定义各平台上可用的系统文本格式控件的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textInputSuggestions(_:)
crawled: 2025-12-02T17:35:21Z
---

# textInputSuggestions(_:)

**Instance Method**

Configures the text input suggestions for this view.

## Declaration

```swift
nonisolated func textInputSuggestions<S>(@ViewBuilder _ suggestions: () -> S) -> some View where S : View

```

## Parameters

- **suggestions**: A view builder that produces content that populates a list of suggestions.

## Discussion

You can suggest text completions during a text input operation by providing a collection of view to this modifier. The interface presents the suggestion views as a list of choices when someone activates the text editing interface.

Associate a string with each suggestion view by adding the [textInputCompletion(_:)](textInputCompletion.zh-Hans.md) modifier to the view.

Use `Label` to get platform-standard visual representations of suggestion text accompanied with images, and `Section` for labelled sections of results.

For example, you can suggest addresses by displaying the venue name, and provide the corresponding address as a text completion in each case:

```swift
TextField("Location", text: $addressText)
    .textInputSuggestions {
        Text("The Fillmore")
            .textInputCompletion("1805 Geary Blvd, San Francisco")
        Text("The Catalyst")
            .textInputCompletion("1011 Pacific Ave, Santa Cruz")
        Text("Rio Theatre")
            .textInputCompletion("1205 Soquel Ave, Santa Cruz")
    }
```

When someone chooses a suggestion, SwiftUI replaces the text in the text field with the text completion string. If you omit the text completion modifier for a particular suggestion view, SwiftUI displays the suggestion, but the suggestion view doesn’t react to taps or clicks.

You can update the suggestions that you provide as conditions change.

For example, you can specify an array of suggestions that you store in a model:

```swift
TextField("Location", text: $addressText)
    .textInputSuggestions {
        ForEach(model.suggestedVenues) { venue in
            Label(venue.name, image: venue.image)
                .textInputCompletion(venue.address)
        }
    }
```

If the model’s `suggestedVenues` begins as an empty array, the interface doesn’t display any suggestions to start. You can then provide logic that updates the array based on some condition. For example, you might update the completions based on the current text. Note that certain events or actions, like when someone moves a macOS window, might dismiss the suggestion view.

## Managing text entry

- **autocorrectionDisabled(_:)**: Sets whether to disable autocorrection for this view.
- **autocorrectionDisabled**: A Boolean value that determines whether the view hierarchy has auto-correction enabled.
- **keyboardType(_:)**: Sets the keyboard type for this view.
- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textInputAutocapitalization(_:)**: Sets how often the shift key in the keyboard is automatically enabled.
- **TextInputAutocapitalization**: The kind of autocapitalization behavior applied during text input.
- **textInputCompletion(_:)**: Associates a fully formed string with the value of this view when used as a text input suggestion
- **textInputSuggestions(_:content:)**: Configures the text input suggestions for this view.
- **textInputSuggestions(_:id:content:)**: Configures the text input suggestions for this view.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on a watchOS device.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on macOS.
- **textContentType(_:)**: Sets the text content type for this view, which the system uses to offer suggestions while the user enters text on an iOS or tvOS device.
- **TextInputFormattingControlPlacement**: A structure defining the system text formatting controls available on each platform.

