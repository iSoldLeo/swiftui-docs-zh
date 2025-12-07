--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityIdentifier(_:isEnabled:)

抓取时间：2025-11-30T20:34:13Z

---

# accessibilityIdentifier(_:isEnabled:)

**实例方法**

使用您指定的字符串来标识视图。

## 声明

```swift
nonisolated func accessibilityIdentifier(_ identifier: String, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **identifier**：要应用的辅助功能标识符。

- **isEnabled**：如果为 true，则应用辅助功能标识符；否则，辅助功能标识符保持不变。

## 说明

此值用于测试。用户不可见。

## 标识元素

- **accessibilityIdentifier(_:)**：使用您指定的字符串来标识视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityIdentifier(_:isEnabled:)
crawled: 2025-11-30T20:34:13Z
---

# accessibilityIdentifier(_:isEnabled:)

**Instance Method**

Uses the string you specify to identify the view.

## Declaration

```swift
nonisolated func accessibilityIdentifier(_ identifier: String, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **identifier**: The accessibility identifier to apply.
- **isEnabled**: If true the accessibility identifier is applied; otherwise the accessibility identifier is unchanged.

## Discussion

Use this value for testing. It isn’t visible to the user.

## Identifying elements

- **accessibilityIdentifier(_:)**: Uses the string you specify to identify the view.

