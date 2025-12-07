---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityRespondsToUserInteraction(_:)
抓取时间： 2025-11-30T21:31:59Z
---

# accessibilityRespondsToUserInteraction(_:)

**实例方法**

明确设置此辅助功能元素是否响应用户交互，从而与开关控制、语音控制或全键盘访问等技术进行交互。

### 声明

```swift
nonisolated func accessibilityRespondsToUserInteraction(_ respondsToUserInteraction: Bool = true) -> ModifiedContent<Content, Modifier>
```

## 讨论

如果未设置此项，则根据辅助功能元素的特性、元素上是否存在辅助功能操作、元素上是否存在手势或包含视图来推断该值。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityRespondsToUserInteraction(_:)
crawled: 2025-11-30T21:31:59Z
---

# accessibilityRespondsToUserInteraction(_:)

**Instance Method**

Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.

## Declaration

```swift
nonisolated func accessibilityRespondsToUserInteraction(_ respondsToUserInteraction: Bool = true) -> ModifiedContent<Content, Modifier>
```

## Discussion

If this is not set, the value is inferred from the traits of the Accessibility element, the presence of Accessibility actions on the element, or the presence of gestures on the element or containing views.

