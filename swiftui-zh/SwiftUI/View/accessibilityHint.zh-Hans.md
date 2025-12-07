--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityHint(_:)

抓取时间：2025-12-02T17:44:26Z

---

# accessibilityHint(_:)

**实例方法**

向用户说明执行视图操作后会发生什么。

## 声明

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

以简短短语的形式提供提示，例如“购买商品”或“下载附件”。

## 提供提示

- **accessibilityHint(_:isEnabled:)**：向用户说明执行视图操作后会发生什么。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityHint(_:)
crawled: 2025-12-02T17:44:26Z
---

# accessibilityHint(_:)

**Instance Method**

Communicates to the user what happens after performing the view’s action.

## Declaration

```swift
nonisolated func accessibilityHint(_ hint: LocalizedStringResource) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

Provide a hint in the form of a brief phrase, like “Purchases the item” or “Downloads the attachment”.

## Offering hints

- **accessibilityHint(_:isEnabled:)**: Communicates to the user what happens after performing the view’s action.

