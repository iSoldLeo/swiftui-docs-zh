--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityHeadingLevel

抓取时间：2025-12-02T17:44:18Z

---

# AccessibilityHeadingLevel

**Enumeration**

标题与其他标题之间的层级关系。

## 声明

```swift
@frozen enum AccessibilityHeadingLevel
```

## 概述

辅助技术可以利用此层级来改善用户在多个标题之间的导航体验。当用户浏览顶级标题时，他们期望每个标题的内容彼此独立。

例如，您可以将可用产品列表分类为“水果”和“蔬菜”等部分。如果仅使用顶级标题，则此列表不需要标题层级关系，您可以使用 [unspecified](AccessibilityHeadingLevel/unspecified.zh-Hans.md) 标题级别。另一方面，如果某个部分包含子部分，例如“水果”部分包含苹果、梨等不同品种的子部分，则应将 [h1](AccessibilityHeadingLevel/h1.zh-Hans.md) 级别应用于“水果和蔬菜”，将 [h2](AccessibilityHeadingLevel/h2.zh-Hans.md) 级别应用于“苹果和梨”。

除 [h1](AccessibilityHeadingLevel/h1.zh-Hans.md) 外，请确保所有分级标题前都带有一个级别低一级的标题。

## 获取标题级别

- **AccessibilityHeadingLevel.h1**：一级标题。

- **AccessibilityHeadingLevel.h2**：二级标题。

- **AccessibilityHeadingLevel.h3**：三级标题。

- **AccessibilityHeadingLevel.h4**：四级标题。

- **AccessibilityHeadingLevel.h5**：五级标题。

- **AccessibilityHeadingLevel.h6**：6 级标题。

- **AccessibilityHeadingLevel.unspecified**：无层级标题。

## 描述内容

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

- **AccessibilityTextContentType**：辅助技术可用于改善语音文本呈现的文本上下文。

## 符合以下标准

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 可等值 (Equatable)

- 可哈希 (Hashable)

- 原始表示 (RawRepresentable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityHeadingLevel
crawled: 2025-12-02T17:44:18Z
---

# AccessibilityHeadingLevel

**Enumeration**

The hierarchy of a heading in relation to other headings.

## Declaration

```swift
@frozen enum AccessibilityHeadingLevel
```

## Overview

Assistive technologies can use this to improve a user’s navigation through multiple headings. When users navigate through top level headings they expect the content for each heading to be unrelated.

For example, you can categorize a list of available products into sections, like Fruits and Vegetables. With only top level headings, this list requires no heading hierarchy, and you use the [unspecified](AccessibilityHeadingLevel/unspecified.zh-Hans.md) heading level. On the other hand, if sections contain subsections, like if the Fruits section has subsections for varieties of Apples, Pears, and so on, you apply the [h1](AccessibilityHeadingLevel/h1.zh-Hans.md) level to Fruits and Vegetables, and the [h2](AccessibilityHeadingLevel/h2.zh-Hans.md) level to Apples and Pears.

Except for [h1](AccessibilityHeadingLevel/h1.zh-Hans.md), be sure to precede all leveled headings by another heading with a level that’s one less.

## Getting the heading level

- **AccessibilityHeadingLevel.h1**: Level 1 heading.
- **AccessibilityHeadingLevel.h2**: Level 2 heading.
- **AccessibilityHeadingLevel.h3**: Level 3 heading.
- **AccessibilityHeadingLevel.h4**: Level 4 heading.
- **AccessibilityHeadingLevel.h5**: Level 5 heading.
- **AccessibilityHeadingLevel.h6**: Level 6 heading.
- **AccessibilityHeadingLevel.unspecified**: A heading without a hierarchy.

## Describing content

- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.
- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **AccessibilityTextContentType**: Textual context that assistive technologies can use to improve the presentation of spoken text.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

