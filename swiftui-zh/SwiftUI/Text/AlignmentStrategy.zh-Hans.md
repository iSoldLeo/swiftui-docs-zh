--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/AlignmentStrategy
抓取时间：2025-12-02T21:48:43Z

---

# Text.AlignmentStrategy

**Structure**

SwiftUI 在未显式提供值的情况下推断文本对齐方式的方法。

## 声明

```swift
struct AlignmentStrategy
```

## 概述

## 类型属性

- **default**：基于上下文的默认策略。

- **layoutBased**：遵循环境设置的对齐方式。

- **writingDirectionBased**：遵循同一段落的书写方向的对齐方式。

## 符合以下规范

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/AlignmentStrategy
crawled: 2025-12-02T21:48:43Z
---

# Text.AlignmentStrategy

**Structure**

The way SwiftUI infers the appropriate text alignment if no value is explicitly provided.

## Declaration

```swift
struct AlignmentStrategy
```

## Overview



## Type Properties

- **default**: The default strategy based on the context it is used in.
- **layoutBased**: The alignment following the environment setting.
- **writingDirectionBased**: The alignment following the writing direction of the same paragraph.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

