--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textSelectionAffinity(_:)

抓取时间：2025-12-02T17:26:06Z

---

# textSelectionAffinity(_:)

**实例方法**

设置选区或光标相对于文本字符的方向。

## 声明

```swift
nonisolated func textSelectionAffinity(_ affinity: TextSelectionAffinity) -> some View

```

## 参数

- **affinity**：要应用的文本选择亲和性策略。

## 返回值

使用指定选择亲和性策略的视图。

## 说明

当需要以特定方式处理换行符、更改光标移动或处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 文字的文本，例如英语和阿拉伯语混合的文本）时，请使用此修饰符。

选择关联性还决定了插入点的位置，例如，在文本跨行换行的情况下，插入点是出现在上一行的最后一个字符之后，还是出现在下一行的第一个字符之前。

假设场景 `hello|مرحبا`，其中 `|` 代表光标，`مرحبا` 代表阿拉伯语的“hello”，则会出现歧义，原因如下：

- 如果光标与英文单词的末尾关联，则相当于继续输入英文（从左到右）。

- 如果光标与阿拉伯语单词的开头关联，则相当于继续输入阿拉伯语（从右到左）。

此修饰符通过确定光标相对于周围文本的方向或关联性来帮助消除这种歧义。

以下示例展示了如何在给定的层级结构中指定特定的选择关联性：

```swift
struct SuggestionTextEditor: View {
    @State var text: String = ""
    @State var selection: TextSelection? = nil

    var body: some View {
        VStack {
            TextEditor(text: $text, selection: $selection)
            // A helper view that offers live suggestions based on selection.
            SuggestionsView(
                substrings: getSubstrings(text: text, indices: selection?.indices))
        }
        .textSelectionAffinity(.upstream)
    }

    private func getSubstrings(
        text: String, indices: TextSelection.Indices?
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```

## 选择文本

- **textSelection(_:)**：控制用户是否可以在此视图中选择文本。

- **TextSelectability**：描述文本选择权限的类型。

- **TextSelection**：表示选定的文本。

- **textSelectionAffinity**：表示选择或光标相对于文本字符的方向或关联性。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 文字的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **TextSelectionAffinity**：表示选择或光标相对于文本字符的方向或关联性。当处理双向文本（包含从左到右和从右到左两种书写方式的文本，例如英语和阿拉伯语的组合）时，这一概念就显得尤为重要。

- **AttributedTextSelection**：表示一段已标注属性的文本。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textSelectionAffinity(_:)
crawled: 2025-12-02T17:26:06Z
---

# textSelectionAffinity(_:)

**Instance Method**

Sets the direction of a selection or cursor relative to a text character.

## Declaration

```swift
nonisolated func textSelectionAffinity(_ affinity: TextSelectionAffinity) -> some View

```

## Parameters

- **affinity**: The text selection affinity strategy to apply.

## Return Value

A view that uses the specified selection affinity strategy.

## Discussion

Use this modifier when you need to handle line breaks in a specific way, alter cursor movement or deal with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).

Selection affinity also determines whether, for example, the insertion point appears after the last character on a line or before the first character on the following line in cases where text wraps across line boundaries.

Given the scenario `hello|مرحبا`, where `|` represents the cursor & `مرحبا` represents “hello” in Arabic, the ambiguity arises because:

- If the cursor is associated with the end of the English word, it would be as if you’re continuing to type in English (LTR).
- If the cursor is associated with the beginning of the Arabic word, it would also be as if you’re continuing to type in Arabic (RTL).

This modifier helps resolve this ambiguity by determining the direction or association of the cursor relative to the surrounding text.

The following example shows how you would specify a specific selection affinity on the given hierarchy:

```swift
struct SuggestionTextEditor: View {
    @State var text: String = ""
    @State var selection: TextSelection? = nil

    var body: some View {
        VStack {
            TextEditor(text: $text, selection: $selection)
            // A helper view that offers live suggestions based on selection.
            SuggestionsView(
                substrings: getSubstrings(text: text, indices: selection?.indices))
        }
        .textSelectionAffinity(.upstream)
    }

    private func getSubstrings(
        text: String, indices: TextSelection.Indices?
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelectability**: A type that describes the ability to select text.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

