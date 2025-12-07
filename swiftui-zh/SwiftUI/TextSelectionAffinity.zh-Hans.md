--- 来源：https://developer.apple.com/documentation/SwiftUI/TextSelectionAffinity
抓取时间：2025-12-02T17:34:38Z

---

# TextSelectionAffinity

**Enumeration**

表示选择或光标相对于文本字符的方向或关联。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 脚本的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

## 声明

```swift
enum TextSelectionAffinity
```

## 概述

例如，当文本跨行换行时，此类型还决定插入点是出现在上一行的最后一个字符之后，还是出现在下一行的第一个字符之前。

假设场景 `hello|مرحبا` 中，`|` 代表光标，`مرحبا` 代表阿拉伯语“hello”，则会产生歧义，原因如下：

- 如果光标与英文单词的末尾关联，则相当于您继续输入英文（从左到右）。

- 如果光标与阿拉伯语单词的开头关联，则相当于您继续输入阿拉伯语（从右到左）。

`TextSelectionAffinity` 通过确定光标相对于周围文本的方向或关联关系来帮助消除这种歧义。

您可以使用 [textSelectionAffinity(_:)](View/textSelectionAffinity.zh-Hans.md) 修饰符配置给定层级的选择关联性：

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

## 枚举类型

- **TextSelectionAffinity.automatic**：框架根据当前上下文确定的选择关联性。

- **TextSelectionAffinity.downstream**：下游选择关联性。在这种情况下，光标与紧随其后的字符关联。

- **TextSelectionAffinity.upstream**：上游选择关联性。在这种情况下，光标与紧随其前的字符关联。

## 选择文本

- **textSelection(_:)**：控制用户是否可以在此视图中选择文本。

- **TextSelectability**：描述文本选择功能的类型。

- **TextSelection**：表示文本的选择。

- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。

- **textSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联关系。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 文字的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **AttributedTextSelection**：表示带属性的文本选区。

## 符合以下规范

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectionAffinity
crawled: 2025-12-02T17:34:38Z
---

# TextSelectionAffinity

**Enumeration**

A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).

## Declaration

```swift
enum TextSelectionAffinity
```

## Overview

This type also determines whether, for example, the insertion point appears after the last character on a line or before the first character on the following line in cases where text wraps across line boundaries.

Given the scenario `hello|مرحبا`, where `|` represents the cursor & `مرحبا` represents “hello” in Arabic, the ambiguity arises because:

- If the cursor is associated with the end of the English word, it would be as if you’re continuing to type in English (LTR).
- If the cursor is associated with the beginning of the Arabic word, it would also be as if you’re continuing to type in Arabic (RTL).

`TextSelectionAffinity` helps resolve this ambiguity by determining the direction or association of the cursor relative to the surrounding text.

You can configure the selection affinity on a given hierarchy by using the [textSelectionAffinity(_:)](View/textSelectionAffinity.zh-Hans.md) modifier:

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

## Enumeration Cases

- **TextSelectionAffinity.automatic**: A selection affinity determined by the framework based on the current context.
- **TextSelectionAffinity.downstream**: An downstream selection affinity. In this case, the cursor is associated with the character immediately after it.
- **TextSelectionAffinity.upstream**: An upstream selection affinity. In this case, the cursor is associated with the character immediately before it.

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelectability**: A type that describes the ability to select text.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

