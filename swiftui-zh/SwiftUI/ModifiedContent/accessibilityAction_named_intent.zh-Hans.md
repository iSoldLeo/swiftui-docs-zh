---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(named:intent:)
抓取时间：2025-11-30T21:31:42Z
---

# accessibilityAction(named:intent:)

**实例方法**

向视图添加标有`name`的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互。执行操作时，`intent` 将被调用。

### 声明

```swift
nonisolated func accessibilityAction<I>(named name: Text, intent: I) -> ModifiedContent<Content, Modifier> where I : AppIntent
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(named:intent:)
crawled: 2025-11-30T21:31:42Z
---

# accessibilityAction(named:intent:)

**Instance Method**

Adds an accessibility action labeled `name` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.

## Declaration

```swift
nonisolated func accessibilityAction<I>(named name: Text, intent: I) -> ModifiedContent<Content, Modifier> where I : AppIntent
```

