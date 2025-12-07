---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityHeading(_:)
抓取时间： 2025-12-02T17:46:57Z
---

# accessibilityHeading(_:)

**实例方法**

设置此标题的级别。

## 声明

```swift
nonisolated func accessibilityHeading(_ level: AccessibilityHeadingLevel) -> ModifiedContent<Content, Modifier>
```

## 参数

- **level**：从可用的 [AccessibilityHeadingLevel](../AccessibilityHeadingLevel.zh-Hans.md) 级别中选出要与该元素关联的标题级别。

## 讨论

使用该修饰符可设置该标题相对于其他标题的级别。系统会将 [h1](../AccessibilityHeadingLevel/h1.zh-Hans.md)至 [h6](../AccessibilityHeadingLevel/h6.zh-Hans.md)的层级数与文本一起显示。

如果不使用该修饰符，默认标题级别为 [unspecified](../AccessibilityHeadingLevel/unspecified.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityHeading(_:)
crawled: 2025-12-02T17:46:57Z
---

# accessibilityHeading(_:)

**Instance Method**

Set the level of this heading.

## Declaration

```swift
nonisolated func accessibilityHeading(_ level: AccessibilityHeadingLevel) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **level**: The heading level to associate with this element from the available [AccessibilityHeadingLevel](../AccessibilityHeadingLevel.zh-Hans.md) levels.

## Discussion

Use this modifier to set the level of this heading in relation to other headings. The system speaks the level number of levels [h1](../AccessibilityHeadingLevel/h1.zh-Hans.md) through [h6](../AccessibilityHeadingLevel/h6.zh-Hans.md) alongside the text.

The default heading level if you don’t use this modifier is [unspecified](../AccessibilityHeadingLevel/unspecified.zh-Hans.md).

