--- 来源：https://developer.apple.com/documentation/SwiftUI/View/journalingSuggestionsPicker(isPresented:onCompletion:)

抓取时间：2025-12-02T17:24:06Z

---

# journalingSuggestionsPicker(isPresented:onCompletion:)

**实例方法**

呈现一个可视化的选择器界面，其中包含用户可以选择以获取更多信息的事件和图像。

## 声明

```swift
@MainActor @preconcurrency func journalingSuggestionsPicker(isPresented: Binding<Bool>, onCompletion: @escaping (JournalingSuggestion) async -> Void) -> some View

```

## 参数

- **isPresented**：绑定到 `Bool` 值，该值决定是否显示选择器。

- **onCompletion**：您提供的代码，用于处理用户在选择器中选择的任何建议。

## 讨论

有关“日记建议”选择器的更多信息，请参阅：doc:presenting-the-suggestions-picker-and-processing-a-selection。


---
source: https://developer.apple.com/documentation/SwiftUI/View/journalingSuggestionsPicker(isPresented:onCompletion:)
crawled: 2025-12-02T17:24:06Z
---

# journalingSuggestionsPicker(isPresented:onCompletion:)

**Instance Method**

Presents a visual picker interface that contains events and images that a person can select to retrieve more information.

## Declaration

```swift
@MainActor @preconcurrency func journalingSuggestionsPicker(isPresented: Binding<Bool>, onCompletion: @escaping (JournalingSuggestion) async -> Void) -> some View

```

## Parameters

- **isPresented**: A binding to a `Bool` value that determines whether to show the picker.
- **onCompletion**: Code that you supply, which processes any suggestions that a person may choose in the picker.

## Discussion

For more information about the Journaling Suggestions picker, see: doc:presenting-the-suggestions-picker-and-processing-a-selection.

