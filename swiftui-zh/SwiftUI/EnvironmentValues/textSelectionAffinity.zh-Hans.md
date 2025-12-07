---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/textSelectionAffinity
抓取时间： 2025-12-02T17:34:37Z
---

# textSelectionAffinity

**实例属性**

表示选择或光标相对于文本字符的方向或关联。在处理双向文本（同时包含 LTR 和 RTL 脚本的文本，如英语和阿拉伯语的组合）时，这一概念变得更加突出。

## 声明

```swift
var textSelectionAffinity: TextSelectionAffinity { get set }
```

## 讨论

您可以使用[textSelectionAffinity(_:)](../View/textSelectionAffinity.zh-Hans.md)修饰符在给定层次结构上配置选择亲和性。

## 选择文本

- **textSelection(_:)**：控制人们是否可以在此视图中选择文本。
- **TextSelectability**：描述选择文本能力的类型。
- **TextSelection**：表示选择文本。
- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。
- **TextSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联。在处理双向文本（同时包含 LTR 和 RTL 脚本的文本，如英语和阿拉伯语合并文本）时，这一概念变得更加突出。
- **AttributedTextSelection**：代表选定的归属文本。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/textSelectionAffinity
crawled: 2025-12-02T17:34:37Z
---

# textSelectionAffinity

**Instance Property**

A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).

## Declaration

```swift
var textSelectionAffinity: TextSelectionAffinity { get set }
```

## Discussion

You can configure the selection affinity on a given hierarchy by using the [textSelectionAffinity(_:)](../View/textSelectionAffinity.zh-Hans.md) modifier.

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelectability**: A type that describes the ability to select text.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

