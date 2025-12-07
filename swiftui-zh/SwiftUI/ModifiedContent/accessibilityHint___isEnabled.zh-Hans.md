---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityHint(_:isEnabled:)
抓取时间： 2025-11-30T21:31:53Z
---

# accessibilityHint(_:isEnabled:)

**实例方法**

向用户传达执行视图操作后的结果。

## 声明

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **hint**：要应用的辅助功能提示。
- **isEnabled**：如果为 true，则应用辅助功能提示；否则辅助功能提示保持不变。

## 讨论

以简短短语的形式提供提示，如 "购买物品 "或 "下载附件"。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityHint(_:isEnabled:)
crawled: 2025-11-30T21:31:53Z
---

# accessibilityHint(_:isEnabled:)

**Instance Method**

Communicates to the user what happens after performing the view’s action.

## Declaration

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **hint**: The accessibility hint to apply.
- **isEnabled**: If true the accessibility hint is applied; otherwise the accessibility hint is unchanged.

## Discussion

Provide a hint in the form of a brief phrase, like “Purchases the item” or “Downloads the attachment”.

