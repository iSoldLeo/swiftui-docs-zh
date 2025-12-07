---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(_:intent:)
抓取时间： 2025-11-30T21:31:41Z
---

# accessibilityAction(_:intent:)

**实例方法**

向视图添加代表`actionKind`的无障碍操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。执行操作时，将调用`intent`。

### 声明

```swift
nonisolated func accessibilityAction<I>(_ actionKind: AccessibilityActionKind = .default, intent: I) -> ModifiedContent<Content, Modifier> where I : AppIntent
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(_:intent:)
crawled: 2025-11-30T21:31:41Z
---

# accessibilityAction(_:intent:)

**Instance Method**

Adds an accessibility action representing `actionKind` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.

## Declaration

```swift
nonisolated func accessibilityAction<I>(_ actionKind: AccessibilityActionKind = .default, intent: I) -> ModifiedContent<Content, Modifier> where I : AppIntent
```

