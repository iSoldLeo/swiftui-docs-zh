--- 来源：https://developer.apple.com/documentation/SwiftUI/TextSelection
抓取时间：2025-12-02T17:34:37Z

---

# TextSelection

**Structure**

表示文本的选中状态。

## 声明

```swift
struct TextSelection
```

## 概述

选中状态可以是插入点（例如文本中的光标）、一段文本的选中状态，或者在 macOS 系统中，可以进行多选。

这通常用于表示在 `TextField` 或 `TextEditor` 中选中的文本。以下示例展示了一个利用文本选择功能，根据当前选中状态提供实时建议的文本编辑器。

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
    }

    private func getSubstrings(
        text: String, indices: TextSelection.Indices?
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```

您还可以使用 [textSelectionAffinity(_:)](View/textSelectionAffinity.zh-Hans.md) 修饰符来指定给定层次结构上的选择关联性：

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

## 初始化器

- **init(insertionPoint:)**：在给定的插入点创建选择。

- **init(range:)**：创建具有给定范围的单个选择。

- **init(ranges:)**：创建具有给定范围集的多个选择。

## 实例属性

- **affinity**：返回选择关联性。

- **indices**：返回当前文本选择的索引。

- **isInsertion**：如果选择是插入点，则返回 `true`。

## 枚举

- **TextSelection.Indices**：当前选区的索引。

## 选择文本

- **textSelection(_:)**：控制用户是否可以在此视图中选择文本。

- **TextSelectability**：描述文本选择功能的类型。

- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。

- **textSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联关系。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 文字的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **TextSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联关系。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 两种书写方式的文本，例如英语和阿拉伯语的组合）时，这一概念就显得尤为重要。

- **AttributedTextSelection**：表示一段已添加属性的文本。

## 符合以下规范：

- 可等值化 (Equatable)

- 可哈希化 (Hashable)


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelection
crawled: 2025-12-02T17:34:37Z
---

# TextSelection

**Structure**

Represents a selection of text.

## Declaration

```swift
struct TextSelection
```

## Overview

A selection is either an insertion point (e.g. a cursor in the text), a selection over a range of text or on macOS, multiple selections.

This is frequently used to represent selection of text in a `TextField` or `TextEditor`. The following example shows a text editor that leverages text selection to offer live suggestions based on the current selection.

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
    }

    private func getSubstrings(
        text: String, indices: TextSelection.Indices?
    ) -> [Substring] {
        // Resolve substrings representing the current selection...
    }
}

struct SuggestionsView: View { ... }
```

You can also use the [textSelectionAffinity(_:)](View/textSelectionAffinity.zh-Hans.md) modifier to specify a selection affinity on the given hierarchy:

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

## Initializers

- **init(insertionPoint:)**: Create a selection at a given insertion point.
- **init(range:)**: Create a single selection with a given range.
- **init(ranges:)**: Create multiple selections with a given range-set.

## Instance Properties

- **affinity**: Return the selection affinity of the selection.
- **indices**: Return the current text selection indices.
- **isInsertion**: Return `true` if the selection is an insertion point.

## Enumerations

- **TextSelection.Indices**: The indices of the current selection.

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelectability**: A type that describes the ability to select text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

## Conforms To

- Equatable
- Hashable

