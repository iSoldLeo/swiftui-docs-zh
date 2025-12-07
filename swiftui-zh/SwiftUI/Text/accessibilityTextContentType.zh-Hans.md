--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/accessibilityTextContentType(_:)

抓取时间：2025-12-02T21:48:41Z

---

# accessibilityTextContentType(_:)

**实例方法**

设置辅助功能文本内容类型。

## 声明

```swift
nonisolated func accessibilityTextContentType(_ value: AccessibilityTextContentType) -> Text
```

## 参数

- **value**：来自可用选项 [AccessibilityTextContentType](../AccessibilityTextContentType.zh-Hans.md) 的辅助功能内容类型。

## 说明

使用此修饰符设置此辅助功能元素的内容类型。辅助技术可以使用此属性选择合适的文本输出方式。例如，当遇到源代码上下文时，VoiceOver 可以选择朗读所有标点符号。

如果您未使用此方法设置值，则默认内容类型为 [plain](../AccessibilityTextContentType/plain.zh-Hans.md)。

## 提供辅助功能信息

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/accessibilityTextContentType(_:)
crawled: 2025-12-02T21:48:41Z
---

# accessibilityTextContentType(_:)

**Instance Method**

Sets an accessibility text content type.

## Declaration

```swift
nonisolated func accessibilityTextContentType(_ value: AccessibilityTextContentType) -> Text
```

## Parameters

- **value**: The accessibility content type from the available [AccessibilityTextContentType](../AccessibilityTextContentType.zh-Hans.md) options.

## Discussion

Use this modifier to set the content type of this accessibility element. Assistive technologies can use this property to choose an appropriate way to output the text. For example, when encountering a source coding context, VoiceOver could choose to speak all punctuation.

If you don’t set a value with this method, the default content type is [plain](../AccessibilityTextContentType/plain.zh-Hans.md).

## Providing accessibility information

- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.

