--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityHint(_:isEnabled:)

抓取时间：2025-11-30T21:29:26Z

---

# accessibilityHint(_:isEnabled:)

**实例方法**

向用户告知执行视图操作后会发生什么。

## 声明

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **hint**：要应用的辅助功能提示。

- **isEnabled**：如果为 true，则应用辅助功能提示；否则，辅助功能提示保持不变。

## 说明

以简短短语的形式提供提示，例如“购买商品”或“下载附件”。

## 提供提示

- **accessibilityHint(_:)**：向用户说明执行视图操作后会发生什么。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityHint(_:isEnabled:)
crawled: 2025-11-30T21:29:26Z
---

# accessibilityHint(_:isEnabled:)

**Instance Method**

Communicates to the user what happens after performing the view’s action.

## Declaration

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource, isEnabled: Bool) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Parameters

- **hint**: The accessibility hint to apply.
- **isEnabled**: If true the accessibility hint is applied; otherwise the accessibility hint is unchanged.

## Discussion

Provide a hint in the form of a brief phrase, like “Purchases the item” or “Downloads the attachment”.

## Offering hints

- **accessibilityHint(_:)**: Communicates to the user what happens after performing the view’s action.

