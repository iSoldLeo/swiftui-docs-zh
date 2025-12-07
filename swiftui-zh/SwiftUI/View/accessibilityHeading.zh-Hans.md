--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityHeading(_:)

抓取时间：2025-12-02T17:44:17Z

---

# accessibilityHeading(_:)

**实例方法**

设置此标题的辅助功能级别。

## 声明

```swift
nonisolated func accessibilityHeading(_ level: AccessibilityHeadingLevel) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **level**：要与此元素关联的标题级别，可用级别为 [AccessibilityHeadingLevel](../AccessibilityHeadingLevel.zh-Hans.md)。

## 说明

使用此修饰符设置此标题相对于其他标题的级别。系统会在文本旁边朗读 [h1](../AccessibilityHeadingLevel/h1.zh-Hans.md) 到 [h6](../AccessibilityHeadingLevel/h6.zh-Hans.md) 的级别编号。

如果您不使用此修饰符，则默认标题级别为 [unspecified](../AccessibilityHeadingLevel/unspecified.zh-Hans.md)。

## 描述内容

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。

- **AccessibilityHeadingLevel**：标题与其他标题之间的层级关系。

- **AccessibilityTextContentType**：辅助技术可用于改善语音文本呈现的文本上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityHeading(_:)
crawled: 2025-12-02T17:44:17Z
---

# accessibilityHeading(_:)

**Instance Method**

Sets the accessibility level of this heading.

## Declaration

```swift
nonisolated func accessibilityHeading(_ level: AccessibilityHeadingLevel) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **level**: The heading level to associate with this element from the available [AccessibilityHeadingLevel](../AccessibilityHeadingLevel.zh-Hans.md) levels.

## Discussion

Use this modifier to set the level of this heading in relation to other headings. The system speaks the level number of levels [h1](../AccessibilityHeadingLevel/h1.zh-Hans.md) through [h6](../AccessibilityHeadingLevel/h6.zh-Hans.md) alongside the text.

The default heading level if you don’t use this modifier is [unspecified](../AccessibilityHeadingLevel/unspecified.zh-Hans.md).

## Describing content

- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.
- **AccessibilityHeadingLevel**: The hierarchy of a heading in relation to other headings.
- **AccessibilityTextContentType**: Textual context that assistive technologies can use to improve the presentation of spoken text.

