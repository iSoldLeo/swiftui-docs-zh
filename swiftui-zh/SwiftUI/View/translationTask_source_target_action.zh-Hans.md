--- 来源：https://developer.apple.com/documentation/SwiftUI/View/translationTask(source:target:action:)

抓取时间：2025-11-30T19:51:35Z

---

# translationTask(source:target:action:)

**实例方法**

添加一个任务，在视图显示之前或指定的源语言或目标语言更改时执行。

## 声明

```swift
nonisolated func translationTask(source: Locale.Language? = nil, target: Locale.Language? = nil, action: @escaping (TranslationSession) async -> Void) -> some View

```

## 参数

- **source**：源内容的语言。如果此值为 `nil`，则会话会尝试识别语言，如果无法识别，则会提示用户选择源语言。会话中翻译的所有文本都应使用相同的源语言。更改此值会取消之前的任务，并创建一个新的会话以再次执行翻译。

- **target**：要将内容翻译成的语言。`nil` 值表示会话根据用户的 `Locale.preferredLanguages` 和 `source` 选择目标语言。更改此值会取消之前的任务并创建一个新任务以再次执行翻译。

- **action**：视图首次出现时以及 `source` 或 `target` 发生更改时运行的闭包。它提供一个 `TranslationSession` 实例来执行一个或多个翻译。

## 讨论

此任务提供一个 `TranslationSession` 实例用于执行翻译。

如果您需要使用相同的 `source` 和 `target` 语言再次执行新的翻译，最好使用 [doc://com.apple.documentation/documentation/SwiftUI/View/translationTask(_:action:)] 并调用 [doc://com.apple.documentation/documentation/Translation/TranslationSession/Configuration/invalidate()]。

例如，您可以在内容出现时进行翻译：

```swift
 struct ContentView: View {
     var sourceText = "Hallo, Welt!"
     var sourceLanguage: Locale.Language?
     var targetLanguage: Locale.Language?

     @State private var targetText: String?

     var body: some View {
         Text(targetText ?? sourceText)
             .translationTask(
                 source: sourceLanguage,
                 target: targetLanguage
             ) { session in
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
```

如果在附加视图消失后使用 `TranslationSession` 实例，或者在更改 `source` 或 `target` 参数后使用该实例，系统将抛出 `fatalError` 异常。这会导致 `action` 闭包提供一个新的 `TranslationSession` 实例。

## 显示翻译

- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**：当满足特定条件时，显示翻译弹出窗口。

- **translationTask(_:action:)**：在显示此视图之前或翻译配置更改时，添加要执行的任务。


---
source: https://developer.apple.com/documentation/SwiftUI/View/translationTask(source:target:action:)
crawled: 2025-11-30T19:51:35Z
---

# translationTask(source:target:action:)

**Instance Method**

Adds a task to perform before this view appears or when the specified source or target languages change.

## Declaration

```swift
nonisolated func translationTask(source: Locale.Language? = nil, target: Locale.Language? = nil, action: @escaping (TranslationSession) async -> Void) -> some View

```

## Parameters

- **source**: The language the source content is in. If this is `nil`, the session tries to identify the language and prompts the person to pick the source language if it’s unclear. All text translated within the session should be in the same source language. Changing this value cancels previous tasks and creates a new session to perform translations again.
- **target**: The language to translate content into. A `nil` value means the session picks a target according to the person’s `Locale.preferredLanguages` and the `source`. Changing this value cancels previous tasks and creates a new one to perform translations again.
- **action**: A closure that runs when the view first appears and when `source` or `target` change.  It provides a `TranslationSession` instance to perform one or multiple translations.

## Discussion

This task provides an instance of `TranslationSession` to use to perform translations.

If you need to perform new translations again with the same `source` and `target` language, it’s better to use [doc://com.apple.documentation/documentation/SwiftUI/View/translationTask(_:action:)] and call [doc://com.apple.documentation/documentation/Translation/TranslationSession/Configuration/invalidate()].

For example, you can translate when content appears:

```swift
 struct ContentView: View {
     var sourceText = "Hallo, Welt!"
     var sourceLanguage: Locale.Language?
     var targetLanguage: Locale.Language?

     @State private var targetText: String?

     var body: some View {
         Text(targetText ?? sourceText)
             .translationTask(
                 source: sourceLanguage,
                 target: targetLanguage
             ) { session in
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
```

The system throws a `fatalError` if you use a `TranslationSession` instance after the attached view disappears or if you use it after changing the `source` or `target` parameters. This causes the `action` closure to provide a new `TranslationSession` instance.

## Showing a translation

- **translationPresentation(isPresented:text:attachmentAnchor:arrowEdge:replacementAction:)**: Presents a translation popover when a given condition is true.
- **translationTask(_:action:)**: Adds a task to perform before this view appears or when the translation configuration changes.

