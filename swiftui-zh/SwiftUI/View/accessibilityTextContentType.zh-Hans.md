--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityTextContentType(_:)

抓取时间：2025-11-30T21:29:17Z

---

# accessibilityTextContentType(_:)

**实例方法**

设置辅助功能文本内容类型。

## 声明

```swift
nonisolated func accessibilityTextContentType(_ value: AccessibilityTextContentType) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **value**：从可用的 [AccessibilityTextContentType](../AccessibilityTextContentType.zh-Hans.md) 选项中选择辅助功能内容类型。

## 说明

使用此修饰符设置此辅助功能元素的内容类型。辅助技术可以使用此属性选择合适的文本输出方式。例如，当遇到源代码上下文时，VoiceOver 可以选择朗读所有标点符号。

默认内容类型为 [plain](../AccessibilityTextContentType/plain.zh-Hans.md)。

## 内容描述

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

- **AccessibilityHeadingLevel**：标题与其他标题之间的层级关系。

- **AccessibilityTextContentType**：辅助技术可用于改善语音文本呈现的文本上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityTextContentType(_:)
crawled: 2025-11-30T21:29:17Z
---

# accessibilityTextContentType(_:)

**Instance Method**

Sets an accessibility text content type.

## Declaration

```swift
nonisolated func accessibilityTextContentType(_ value: AccessibilityTextContentType) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **value**: The accessibility content type from the available [AccessibilityTextContentType](../AccessibilityTextContentType.zh-Hans.md) options.

## Discussion

Use this modifier to set the content type of this accessibility element. Assistive technologies can use this property to choose an appropriate way to output the text. For example, when encountering a source coding context, VoiceOver could choose to speak all punctuation.

The default content type [plain](../AccessibilityTextContentType/plain.zh-Hans.md).

## Describing content

- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **AccessibilityHeadingLevel**: The hierarchy of a heading in relation to other headings.
- **AccessibilityTextContentType**: Textual context that assistive technologies can use to improve the presentation of spoken text.

