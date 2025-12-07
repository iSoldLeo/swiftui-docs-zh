--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/WritingDirectionStrategy

抓取时间：2025-12-02T21:48:45Z

---

# Text.WritingDirectionStrategy

**Structure**

SwiftUI 在未显式提供值的情况下推断合适的书写方向的方式。

## 声明

```swift
struct WritingDirectionStrategy
```

## 类型属性

- **contentBased**：遵循布局字符串语言的书写方向。

- **default**：默认策略为 [contentBased](WritingDirectionStrategy/contentBased.zh-Hans.md)。

- **layoutBased**：遵循 UI 整体布局方向的书写方向。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Text/WritingDirectionStrategy
crawled: 2025-12-02T21:48:45Z
---

# Text.WritingDirectionStrategy

**Structure**

The way SwiftUI infers the appropriate writing direction if no value is explicitly provided.

## Declaration

```swift
struct WritingDirectionStrategy
```

## Type Properties

- **contentBased**: The writing direction following the language of the string that is laid out.
- **default**: The default strategy is [contentBased](WritingDirectionStrategy/contentBased.zh-Hans.md).
- **layoutBased**: The writing direction following the general UI layout direction.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

