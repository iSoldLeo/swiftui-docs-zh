---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityTextContentType(_:)
抓取时间： 2025-12-02T17:47:10Z
---

# accessibilityTextContentType(_:)

**实例方法**

设置无障碍文本内容类型。

## 声明

```swift
nonisolated func accessibilityTextContentType(_ textContentType: AccessibilityTextContentType) -> ModifiedContent<Content, Modifier>
```

## 讨论

使用此修饰符可设置此辅助功能元素的内容类型。辅助技术可使用此属性选择适当的文本输出方式。例如，在遇到源编码上下文时，VoiceOver 可以选择说出所有标点符号。

默认内容类型[plain](../AccessibilityTextContentType/plain.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityTextContentType(_:)
crawled: 2025-12-02T17:47:10Z
---

# accessibilityTextContentType(_:)

**Instance Method**

Sets an accessibility text content type.

## Declaration

```swift
nonisolated func accessibilityTextContentType(_ textContentType: AccessibilityTextContentType) -> ModifiedContent<Content, Modifier>
```

## Discussion

Use this modifier to set the content type of this accessibility element. Assistive technologies can use this property to choose an appropriate way to output the text. For example, when encountering a source coding context, VoiceOver could choose to speak all punctuation.

The default content type [plain](../AccessibilityTextContentType/plain.zh-Hans.md).

