--- 来源：https://developer.apple.com/documentation/SwiftUI/View/translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)

抓取时间：2025-11-30T19:51:33Z

---

# translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)

**实例方法**

当给定条件为真时，显示翻译弹出框。

## 声明

```swift
nonisolated func translationPresentation(isPresented: Binding<Bool>, text: String, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge = .top, replacementAction: ((String) -> Void)? = nil) -> some View

```

## 参数

- **isPresented**：绑定到一个布尔值，用于确定是否显示弹出框。

- **text**：要翻译的文本。在弹出框显示后更改此值无效。

- **attachmentAnchor**：定义弹出框连接点的定位锚点。默认值为 [doc://com.apple.documentation/documentation/SwiftUI/Anchor/Source/bounds]。

- **arrowEdge**：定义 macOS 系统中弹出框箭头位置的 `attachmentAnchor` 边缘。默认值为 [doc://com.apple.documentation/documentation/SwiftUI/Edge/top]。iOS 系统忽略此参数。

- **replacementAction**：用户与“替换为翻译”按钮交互时要执行的可选操作。启用此操作后，“替换为翻译”按钮才会显示。

## 讨论

当 `translationVisible` 布尔变量为 `true` 时，使用此方法显示系统 UI 翻译弹出框。将此视图修饰符附加到包含要翻译文本的视图。然后，将布尔绑定 `isPresented` 设置为 `true`，即可显示弹出窗口。设置完成后，系统界面会出现一个翻译弹出窗口，提供翻译选项。

在下面的示例中，当用户按下“翻译”按钮切换 `translationVisible` 状态变量时，弹出窗口就会出现。

```swift
struct ContentView: View {
    @State private var translationVisible = false
    private var originalText = "Hallo, Welt!"

    var body: some View {
        VStack {
            Text(verbatim: originalText)
                .translationPresentation(isPresented: $translationVisible, text: originalText)
            Button("Translate") {
                translationVisible.toggle()
            }
        }
    }
}
```

要将原文替换为翻译，请将一个尾随闭包传递给 `replacementAction` 参数。这样，系统界面中会出现一个“替换为翻译”按钮。用户点击此按钮后，闭包会返回一个字符串形式的翻译文本。使用该字符串将原文更新为翻译后的文本，如下所示：

```swift
struct ReplaceTranslation: View {
    @State private var translationVisible = false
    @State private var originalText = "Hallo, Welt!"

    var body: some View {
        VStack(spacing: 20) {
            TextField("Text to translate", text: $originalText, axis: .vertical)
                .textFieldStyle(.roundedBorder)
                .translationPresentation(isPresented: $translationVisible, text: originalText) { translatedString in
                    // Update the original text with the translated result.
                    originalText = translatedString
                }
            Button("Translate") {
                translationVisible.toggle()
            }
        }
        .padding()
    }
}
```

如果系统无法检测到源语言，则会提示用户选择要翻译的语言。支持的语言列表请参见 `LanguageAvailability.supportedLanguages`。

虽然此功能支持长文本字符串，但处理短文本（不超过几句话或几个短语）效果最佳。

## 显示翻译

- **translationTask(_:action:)**：添加一项任务，在显示此视图之前或翻译配置更改时执行。

- **translationTask(source:target:action:)**：添加一项任务，在显示此视图之前或指定的源语言或目标语言更改时执行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)
crawled: 2025-11-30T19:51:33Z
---

# translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)

**Instance Method**

Presents a translation popover when a given condition is true.

## Declaration

```swift
nonisolated func translationPresentation(isPresented: Binding<Bool>, text: String, attachmentAnchor: PopoverAttachmentAnchor = .rect(.bounds), arrowEdge: Edge = .top, replacementAction: ((String) -> Void)? = nil) -> some View

```

## Parameters

- **isPresented**: A binding to a Boolean value that determines whether to present the popover.
- **text**: The text to be translated. Changing this after the popover presents has no effect.
- **attachmentAnchor**: The positioning anchor that defines the attachment point of the popover. The default is [doc://com.apple.documentation/documentation/SwiftUI/Anchor/Source/bounds].
- **arrowEdge**: The edge of the `attachmentAnchor` that defines the location of the popover’s arrow in macOS. The default is [doc://com.apple.documentation/documentation/SwiftUI/Edge/top]. iOS ignores this parameter.
- **replacementAction**: An optional action to perform when someone interacts with the “Replace with Translation” button. The “Replace with Translation” button appears when you provide this action.

## Discussion

Use this method to show a system UI translation popover when the `translationVisible` Boolean variable is `true`. Attach this view modifier to the containing view holding the text to translate. Then set the `isPresented` Boolean binding to `true` when you want the popover to display. When you do, a system UI translation popover appears offering a translation.

In the example below, the popover appears when the user toggles the `translationVisible` state variable by pressing the Translate button.

```swift
struct ContentView: View {
    @State private var translationVisible = false
    private var originalText = "Hallo, Welt!"

    var body: some View {
        VStack {
            Text(verbatim: originalText)
                .translationPresentation(isPresented: $translationVisible, text: originalText)
            Button("Translate") {
                translationVisible.toggle()
            }
        }
    }
}
```

To replace the original text with the translation, pass in a trailing closure to the `replacementAction` parameter. When you do, a Replace with Translation button appears in the system UI. When the user taps this button, the closure returns a translation of the text as a string. Use that string to update the original text with the translated text as shown below:

```swift
struct ReplaceTranslation: View {
    @State private var translationVisible = false
    @State private var originalText = "Hallo, Welt!"

    var body: some View {
        VStack(spacing: 20) {
            TextField("Text to translate", text: $originalText, axis: .vertical)
                .textFieldStyle(.roundedBorder)
                .translationPresentation(isPresented: $translationVisible, text: originalText) { translatedString in
                    // Update the original text with the translated result.
                    originalText = translatedString
                }
            Button("Translate") {
                translationVisible.toggle()
            }
        }
        .padding()
    }
}
```

If the system can’t detect the source language, it asks the user to select the language to translate from. For a list of supported languages see `LanguageAvailability.supportedLanguages`.

While this function does support long strings of text, it works best with short ones (no more than a couple of sentences or phrases in length).

## Showing a translation

- **translationTask(_:action:)**: Adds a task to perform before this view appears or when the translation configuration changes.
- **translationTask(source:target:action:)**: Adds a task to perform before this view appears or when the specified source or target languages change.

