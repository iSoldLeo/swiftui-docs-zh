--- 来源：https://developer.apple.com/documentation/SwiftUI/View/translationTask(_:action:)

抓取时间：2025-12-02T16:05:45Z

---

# translationTask(_:action:)

**实例方法**

添加一个任务，在视图显示之前或翻译配置更改时执行。

## 声明

```swift
nonisolated func translationTask(_ configuration: TranslationSession.Configuration?, action: @escaping (TranslationSession) async -> Void) -> some View

```

## 参数

- **configuration**：`TranslationSession` 的配置。当此配置不为空且发生更改时，`action` 将运行，并提供 `TranslationSession` 的实例来执行翻译。

- **action**：当 `configuration` 非空且发生变化时，此闭包运行。如果 `configuration` 初始值非空，则在视图出现时调用操作闭包，并提供一个 `TranslationSession` 实例来执行一个或多个翻译。

## 讨论

此任务提供一个 `TranslationSession` 实例用于翻译。每当 [doc://com.apple.documentation/documentation/Translation/TranslationSession/Configuration] 发生变化且不是 `nil` 时，闭包 `action` 运行，并提供一个 `TranslationSession` 实例来执行一个或多个翻译。

例如，您可以创建一个 [doc://com.apple.documentation/documentation/Translation/TranslationSession/Configuration] 来响应按钮按下以触发翻译：

```swift
struct ContentView: View {
    @State private var sourceText = "Hallo, Welt!"
    var sourceLanguage: Locale.Language?
    var targetLanguage: Locale.Language?

    @State private var targetText: String?
    @State private var configuration: TranslationSession.Configuration?

    var body: some View {
        VStack {
            Text(targetText ?? sourceText)
            Button("Translate") {
                guard configuration == nil else {
                    configuration?.invalidate()
                    return
                }

                 configuration = TranslationSession.Configuration(
                    source: sourceLanguage,
                    target: targetLanguage)
            }
            .translationTask(configuration) { session in
                Task { @MainActor in
                    do {
                        let response = try await session.translate(sourceText)
                        targetText = response.targetText
                    } catch {
                        // code to handle error
                    }
                }
            }
        }
    }
}
```

如果在附加视图消失后或更改 `configuration` 后使用 `TranslationSession` 实例，系统将抛出 `fatalError` 异常。这会导致 `action` 闭包提供一个新的 `TranslationSession` 实例。

## 显示翻译

- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**：当给定条件为真时，显示翻译弹出窗口。

- **translationTask(source:target:action:)**：添加一个任务，在该视图显示之前或指定的源语言或目标语言更改时执行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/translationTask(_:action:)
crawled: 2025-12-02T16:05:45Z
---

# translationTask(_:action:)

**Instance Method**

Adds a task to perform before this view appears or when the translation configuration changes.

## Declaration

```swift
nonisolated func translationTask(_ configuration: TranslationSession.Configuration?, action: @escaping (TranslationSession) async -> Void) -> some View

```

## Parameters

- **configuration**: A configuration for a `TranslationSession`. When this configuration is non-nil and changes, the `action` runs providing an instance of `TranslationSession` to perform translations.
- **action**: This closure runs when the `configuration` is non-nil and changes. If the `configuration` is initially non-nil, it calls the action closure when the view appears and provides a `TranslationSession` instance to perform one or multiple translations.

## Discussion

This task provides an instance of `TranslationSession` to use in translations. Whenever [doc://com.apple.documentation/documentation/Translation/TranslationSession/Configuration]  changes and isn’t `nil`, the closure `action` runs, providing a `TranslationSession` instance to perform one or more translations.

For example, you can create a [doc://com.apple.documentation/documentation/Translation/TranslationSession/Configuration] in response to a button press to trigger translation:

```swift
struct ContentView: View {
    @State private var sourceText = "Hallo, Welt!"
    var sourceLanguage: Locale.Language?
    var targetLanguage: Locale.Language?

    @State private var targetText: String?
    @State private var configuration: TranslationSession.Configuration?

    var body: some View {
        VStack {
            Text(targetText ?? sourceText)
            Button("Translate") {
                guard configuration == nil else {
                    configuration?.invalidate()
                    return
                }

                 configuration = TranslationSession.Configuration(
                    source: sourceLanguage,
                    target: targetLanguage)
            }
            .translationTask(configuration) { session in
                Task { @MainActor in
                    do {
                        let response = try await session.translate(sourceText)
                        targetText = response.targetText
                    } catch {
                        // code to handle error
                    }
                }
            }
        }
    }
}
```

The system throws a `fatalError` if you use a `TranslationSession` instance after the attached view disappears or if you use it after changing the `configuration`. This causes the `action` closure to provide a new `TranslationSession` instance.

## Showing a translation

- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**: Presents a translation popover when a given condition is true.
- **translationTask(source:target:action:)**: Adds a task to perform before this view appears or when the specified source or target languages change.

