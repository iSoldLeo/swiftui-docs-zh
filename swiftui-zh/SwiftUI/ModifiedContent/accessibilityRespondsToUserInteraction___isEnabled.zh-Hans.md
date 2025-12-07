---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityRespondsToUserInteraction(_:isEnabled:)
抓取时间：2025-11-30T21:32:00Z
---

# accessibilityRespondsToUserInteraction(_:isEnabled:)

**实例方法**

明确设置此辅助功能元素是否响应用户交互，从而与开关控制、语音控制或全键盘访问等技术进行交互。

### 声明

```swift
nonisolated func accessibilityRespondsToUserInteraction(_ respondsToUserInteraction: Bool, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## 参数

- **respondsToUserInteraction**：视图是否响应用户交互。
- **isEnabled**：如果为 true，则应用无障碍交互状态；否则，无障碍交互状态保持不变。

## 讨论

如果未设置此项，则会根据无障碍元素的特质、元素上是否存在无障碍操作、元素上是否存在手势或包含视图来推断该值。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityRespondsToUserInteraction(_:isEnabled:)
crawled: 2025-11-30T21:32:00Z
---

# accessibilityRespondsToUserInteraction(_:isEnabled:)

**Instance Method**

Explicitly set whether this Accessibility element responds to user interaction and would thus be interacted with by technologies such as Switch Control, Voice Control or Full Keyboard Access.

## Declaration

```swift
nonisolated func accessibilityRespondsToUserInteraction(_ respondsToUserInteraction: Bool, isEnabled: Bool) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **respondsToUserInteraction**: Whether the view responds to user interaction.
- **isEnabled**: If true the accessibility interaction state is applied; otherwise the accessibility interaction state is unchanged.

## Discussion

If this is not set, the value is inferred from the traits of the Accessibility element, the presence of Accessibility actions on the element, or the presence of gestures on the element or containing views.

