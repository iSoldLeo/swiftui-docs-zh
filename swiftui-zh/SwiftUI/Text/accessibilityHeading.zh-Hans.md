--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/accessibilityHeading(_:)

抓取时间：2025-12-01T02:39:30Z

---

# accessibilityHeading(_:)

**实例方法**

设置此标题的辅助功能级别。

## 声明

```swift
nonisolated func accessibilityHeading(_ level: AccessibilityHeadingLevel) -> Text
```

## 参数

- **level**：要与此元素关联的标题级别，可用级别为 [AccessibilityHeadingLevel](../AccessibilityHeadingLevel.zh-Hans.md)。

## 说明

使用此修饰符设置此标题相对于其他标题的级别。系统会在文本旁边朗读 [h1](../AccessibilityHeadingLevel/h1.zh-Hans.md) 到 [h6](../AccessibilityHeadingLevel/h6.zh-Hans.md) 的级别编号。

如果您不使用此修饰符，则默认标题级别为 [unspecified](../AccessibilityHeadingLevel/unspecified.zh-Hans.md)。

## 提供辅助功能信息

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/accessibilityHeading(_:)
crawled: 2025-12-01T02:39:30Z
---

# accessibilityHeading(_:)

**Instance Method**

Sets the accessibility level of this heading.

## Declaration

```swift
nonisolated func accessibilityHeading(_ level: AccessibilityHeadingLevel) -> Text
```

## Parameters

- **level**: The heading level to associate with this element from the available [AccessibilityHeadingLevel](../AccessibilityHeadingLevel.zh-Hans.md) levels.

## Discussion

Use this modifier to set the level of this heading in relation to other headings. The system speaks the level number of levels [h1](../AccessibilityHeadingLevel/h1.zh-Hans.md) through [h6](../AccessibilityHeadingLevel/h6.zh-Hans.md) alongside the text.

The default heading level if you don’t use this modifier is [unspecified](../AccessibilityHeadingLevel/unspecified.zh-Hans.md).

## Providing accessibility information

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.

