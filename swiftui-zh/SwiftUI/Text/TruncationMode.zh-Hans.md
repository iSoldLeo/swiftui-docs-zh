--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/TruncationMode

抓取时间：2025-12-02T21:48:35Z

---

# Text.TruncationMode

**Enumeration**

当文本行过长而无法容纳在可用空间中时，应用此截断类型。

## 声明

```swift
enum TruncationMode
```

## 概述

当文本视图包含的文本超过其显示空间时，视图可能会截断文本并在截断点处放置省略号 (…)。使用 [truncationMode(_:)](../View/truncationMode.zh-Hans.md) 修饰符以及 `TruncationMode` 值之一来指定要截断的文本部分，可以是开头、中间或结尾。

## 获取文本截断模式

- **Text.TruncationMode.head**：在行首截断。

- **Text.TruncationMode.middle**：在行中截断。

- **Text.TruncationMode.tail**：在行尾截断。

## 将文本适配到可用空间

- **textScale(_:isEnabled:)**：对文本应用缩放比例。

- **Text.Scale**：定义文本缩放比例

## 符合以下规范

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/TruncationMode
crawled: 2025-12-02T21:48:35Z
---

# Text.TruncationMode

**Enumeration**

The type of truncation to apply to a line of text when it’s too long to fit in the available space.

## Declaration

```swift
enum TruncationMode
```

## Overview

When a text view contains more text than it’s able to display, the view might truncate the text and place an ellipsis (…) at the truncation point. Use the [truncationMode(_:)](../View/truncationMode.zh-Hans.md) modifier with one of the `TruncationMode` values to indicate which part of the text to truncate, either at the beginning, in the middle, or at the end.

## Getting text truncation modes

- **Text.TruncationMode.head**: Truncate at the beginning of the line.
- **Text.TruncationMode.middle**: Truncate in the middle of the line.
- **Text.TruncationMode.tail**: Truncate at the end of the line.

## Fitting text into available space

- **textScale(_:isEnabled:)**: Applies a text scale to the text.
- **Text.Scale**: Defines text scales

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

