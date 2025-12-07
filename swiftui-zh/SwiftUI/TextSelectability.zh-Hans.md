---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelectability
抓取时间： 2025-12-02T17:34:36Z
---

# 文本可选性

**Protocol**

描述文本选择能力的类型。

## 声明

```swift
protocol TextSelectability
```

## 概览

要配置用户是否可以在应用程序中选择文本，请使用[textSelection(_:)](View/textSelection.zh-Hans.md)修饰符，并传递一个文本选择性值，如 [enabled](TextSelectability/enabled.zh-Hans.md) 或 [disabled](TextSelectability/disabled.zh-Hans.md)。

## 获取可选择性选项

- **enabled**：可选性值，可让使用您应用程序的人选择文本。
- **disabled**：选择性值，用于禁止使用您应用程序的人选择文本。

## 指定可选择性

- **allowsSelection**：布尔值，表示选择性类型是否允许选择。

## 支持的类型

- **EnabledTextSelectability**：选择性类型，可让使用应用程序的人选择文本。
- **DisabledTextSelectability**：可选类型，用于禁止使用您应用程序的用户选择文本。

## 选择文本

- **textSelection(_:)**：控制用户是否可以在此视图中选择文本。
- **TextSelection**：表示选择文本。
- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。
- **textSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联。在处理双向文本（同时包含 LTR 和 RTL 脚本的文本，如英语和阿拉伯语的组合）时，这一概念变得更加突出。
- **TextSelectionAffinity**：表示选择或光标相对于文本字符的方向或关联。在处理双向文本（同时包含 LTR 和 RTL 脚本的文本，如英语和阿拉伯语的组合文本）时，这一概念变得更加突出。
- **AttributedTextSelection**：代表选定的归属文本。

## 符合类型

- 禁用文本可选性
- 启用文本可选性


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectability
crawled: 2025-12-02T17:34:36Z
---

# TextSelectability

**Protocol**

A type that describes the ability to select text.

## Declaration

```swift
protocol TextSelectability
```

## Overview

To configure whether people can select text in your app, use the [textSelection(_:)](View/textSelection.zh-Hans.md) modifier, passing in a text selectability value like [enabled](TextSelectability/enabled.zh-Hans.md) or [disabled](TextSelectability/disabled.zh-Hans.md).

## Getting selectability options

- **enabled**: A selectability value that enables text selection by a person using your app.
- **disabled**: A selectability value that disables text selection by the person using your app.

## Specifying selectability

- **allowsSelection**: A Boolean value that indicates whether the selectability type allows selection.

## Supporting types

- **EnabledTextSelectability**: A selectability type that enables text selection by the person using your app.
- **DisabledTextSelectability**: A selectability type that disables text selection by the person using your app.

## Selecting text

- **textSelection(_:)**: Controls whether people can select text within this view.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

## Conforming Types

- DisabledTextSelectability
- EnabledTextSelectability

