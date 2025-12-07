---

来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRespondsToUserInteraction(_:)

抓取时间：2025-12-02T17:44:08Z

---

# accessibilityRespondsToUserInteraction(_:)

**实例方法**

显式设置此辅助功能元素是否响应用户交互，从而是否可通过切换控制、语音控制或完整键盘访问等技术进行交互。

## 声明

```swift
nonisolated func accessibilityRespondsToUserInteraction(_ respondsToUserInteraction: Bool = true) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 说明

如果未设置此值，则会根据辅助功能元素的特性、元素上是否存在辅助功能操作或元素及其包含视图上是否存在手势来推断该值。

## 管理交互性

- **accessibilityRespondsToUserInteraction(_:isEnabled:)**：明确设置此辅助功能元素是否响应用户交互，从而是否可通过诸如开关控制、语音控制或全键盘访问等技术进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRespondsToUserInteraction(_:)
crawled: 2025-12-02T17:44:08Z
---

# accessibilityRespondsToUserInteraction(_:)

**Instance Method**

Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.

## Declaration

```swift
nonisolated func accessibilityRespondsToUserInteraction(_ respondsToUserInteraction: Bool = true) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## Discussion

If this is not set, the value is inferred from the traits of the Accessibility element, the presence of Accessibility actions on the element, or the presence of gestures on the element or containing views.

## Managing interactivity

- **accessibilityRespondsToUserInteraction(_:isEnabled:)**: Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.

