---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection
抓取时间： 2025-12-02T17:34:39Z
---

# 属性文本选择

**Structure**

代表选定的归属文本。

### 声明

```swift
struct AttributedTextSelection
```

## 概览

选区可以是一个插入点（如文本中的光标），也可以是一个字符范围。虽然该范围在视觉上总是连续的，但在文本存储中可能在逻辑上并不连续。具体来说，一个选择值不能代表多个光标。

这通常用于表示`TextEditor`中的文本选择。下面的示例显示了一个文本编辑器，它利用文本选择功能，根据当前选择提供实时建议。

```swift
struct SuggestionTextEditor: View {
    @State var text: AttributedString = ""
    @State var selection = AttributedTextSelection()

    var body: some View {
        VStack {
            TextEditor(text: $text, selection: $selection)
            // A helper view that offers live suggestions based on selection.
            SuggestionsView(substrings: getSubstrings(
                text: text, indices: selection.indices(in: text))
        }
    }

    private func getSubstrings(
        text: String, indices: AttributedTextSelection.Indices
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```

您还可以使用[textSelectionAffinity(_:)](View/textSelectionAffinity.zh-Hans.md)修饰符在给定的层次结构上指定选择亲和性：

```swift
struct SuggestionTextEditor: View {
    @State var text: AttributedString = ""
    @State var selection = AttributedTextSelection()

    var body: some View {
        VStack {
            TextEditor(text: $text, selection: $selection)
            // A helper view that offers live suggestions based on selection.
            SuggestionsView(substrings: getSubstrings(
                text: text, indices: selection.indices(in: text))
        }
        .textSelectionAffinity(.upstream)
    }

    private func getSubstrings(
        text: String, indices: AttributedTextSelection.Indices
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```



## 结构

- **AttributedTextSelection.Attributes**：某个文本中某个选区所有属性值的序列。

## 初始化器

- **init()**：初始化新文本编辑器的默认选区。
- **init(insertionPoint:typingAttributes:)**：将选区初始化为单个插入点。
- **init(range:)**：将选区初始化为字符范围。
- **init(ranges:)**：将选区初始化为字符范围。

### 实例方法

- **affinity(in:)**：返回选区的亲和度。
- **attributes(in:)**：获取选区在给定文本中所有属性值的懒序列。
- **indices(in:)**：当前文本选区的索引。
- **typingAttributes(in:)**：返回相应文本的键入属性。

## 枚举

- **AttributedTextSelection.Indices**：当前选区的索引。

## 选择文本

- **textSelection(_:)**：控制是否可以在此视图中选择文本。
- **TextSelectability**：描述选择文本能力的类型。
- **TextSelection**：表示选择文本。
- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。
- **textSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联。在处理双向文本（同时包含 LTR 和 RTL 脚本的文本，如英语和阿拉伯语的组合）时，这一概念变得更加突出。
- **TextSelectionAffinity**：表示选择或光标相对于文本字符的方向或关联。在处理双向文本（同时包含 LTR 和 RTL 脚本的文本，如英语和阿拉伯语的组合文本）时，这一概念变得更加突出。

## 符合

- 等同
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextSelection
crawled: 2025-12-02T17:34:39Z
---

# AttributedTextSelection

**Structure**

Represents a selection of attributed text.

## Declaration

```swift
struct AttributedTextSelection
```

## Overview

A selection is either an insertion point (e.g. a cursor in the text), or spans over a range of characters. While that range is always visually contiguous, it may not be logically contiguous in the text storage. Specifically, a single selection value cannot represent multiple cursors.

This is frequently used to represent selection of text in a `TextEditor`. The following example shows a text editor that leverages text selection to offer live suggestions based on the current selection.

```swift
struct SuggestionTextEditor: View {
    @State var text: AttributedString = ""
    @State var selection = AttributedTextSelection()

    var body: some View {
        VStack {
            TextEditor(text: $text, selection: $selection)
            // A helper view that offers live suggestions based on selection.
            SuggestionsView(substrings: getSubstrings(
                text: text, indices: selection.indices(in: text))
        }
    }

    private func getSubstrings(
        text: String, indices: AttributedTextSelection.Indices
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```

You can also use the [textSelectionAffinity(_:)](View/textSelectionAffinity.zh-Hans.md) modifier to specify a selection affinity on the given hierarchy:

```swift
struct SuggestionTextEditor: View {
    @State var text: AttributedString = ""
    @State var selection = AttributedTextSelection()

    var body: some View {
        VStack {
            TextEditor(text: $text, selection: $selection)
            // A helper view that offers live suggestions based on selection.
            SuggestionsView(substrings: getSubstrings(
                text: text, indices: selection.indices(in: text))
        }
        .textSelectionAffinity(.upstream)
    }

    private func getSubstrings(
        text: String, indices: AttributedTextSelection.Indices
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```



## Structures

- **AttributedTextSelection.Attributes**: A sequence of all attribute values a selection has in a certain text.

## Initializers

- **init()**: Initialize the default selection for a new text editor.
- **init(insertionPoint:typingAttributes:)**: Initialize a selection to a single insertion point.
- **init(range:)**: Initialize a selection to a character range.
- **init(ranges:)**: Initialize a selection to character ranges.

## Instance Methods

- **affinity(in:)**: Return the selection affinity of the selection.
- **attributes(in:)**: Obtain a lazy sequence of all attribute values the selection has in a given text.
- **indices(in:)**: The current text selection indices.
- **typingAttributes(in:)**: Returns the typing attributes for a corresponding text.

## Enumerations

- **AttributedTextSelection.Indices**: The indices of the current selection.

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelectability**: A type that describes the ability to select text.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).

## Conforms To

- Equatable
- Sendable
- SendableMetatype

