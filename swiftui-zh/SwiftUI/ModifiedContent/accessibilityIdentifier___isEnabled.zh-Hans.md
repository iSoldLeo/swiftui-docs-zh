---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityIdentifier(_:isEnabled:)
抓取时间： 2025-12-02T17:47:02Z
---

# accessibilityIdentifier(_:isEnabled:)

**实例方法**

使用您指定的字符串来标识视图。

## 声明

```swift
nonisolated func accessibilityIdentifier(_ identifier: String, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **identifier**：要应用的可访问性标识符。
- **isEnabled**：如果为 true，则应用辅助功能标识符；否则辅助功能标识符保持不变。

## 讨论

使用此值进行测试。用户看不到它。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityIdentifier(_:isEnabled:)
crawled: 2025-12-02T17:47:02Z
---

# accessibilityIdentifier(_:isEnabled:)

**Instance Method**

Uses the string you specify to identify the view.

## Declaration

```swift
nonisolated func accessibilityIdentifier(_ identifier: String, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **identifier**: The accessibility identifier to apply.
- **isEnabled**: If true the accessibility identifier is applied; otherwise the accessibility identifier is unchanged.

## Discussion

Use this value for testing. It isn’t visible to the user.

