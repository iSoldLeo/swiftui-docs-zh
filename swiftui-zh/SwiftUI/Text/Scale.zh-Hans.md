--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/Scale
抓取时间：2025-12-02T21:48:35Z

---

# Text.Scale

**Structure**

定义文本缩放比例

## 声明

```swift
struct Scale
```

## 概述

文本缩放比例提供了一种方法，可以根据所使用的基础字体选择合适的文本缩放比例。

## 获取内置文本缩放比例

- **default**：定义默认文本缩放比例

- **secondary**：定义辅助文本缩放比例

## 将文本适配到可用空间

- **textScale(_:isEnabled:)**：将文本缩放比例应用于文本。

- **Text.TruncationMode**：当文本行过长而无法容纳在可用空间时，要应用的截断类型。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/Scale
crawled: 2025-12-02T21:48:35Z
---

# Text.Scale

**Structure**

Defines text scales

## Declaration

```swift
struct Scale
```

## Overview

Text scale provides a way to pick a logical text scale relative to the base font which is used.

## Getting built-in text scales

- **default**: Defines default text scale
- **secondary**: Defines secondary text scale

## Fitting text into available space

- **textScale(_:isEnabled:)**: Applies a text scale to the text.
- **Text.TruncationMode**: The type of truncation to apply to a line of text when it’s too long to fit in the available space.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

