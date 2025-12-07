---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(_:_:)
抓取时间： 2025-12-02T17:46:45Z
---

# accessibilityAction(_:_:)

**实例方法**

为视图添加辅助操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。

### 声明

```swift
nonisolated func accessibilityAction(_ actionKind: AccessibilityActionKind = .default, _ handler: @escaping () -> Void) -> ModifiedContent<Content, Modifier>
```

## 讨论

例如，可以在视图中添加`.default` 操作来撰写新邮件。

```swift
var body: some View {
    ContentView()
        .accessibilityAction {
            // Handle action
        }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(_:_:)
crawled: 2025-12-02T17:46:45Z
---

# accessibilityAction(_:_:)

**Instance Method**

Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityAction(_ actionKind: AccessibilityActionKind = .default, _ handler: @escaping () -> Void) -> ModifiedContent<Content, Modifier>
```

## Discussion

For example, this is how a `.default` action to compose a new email could be added to a view.

```swift
var body: some View {
    ContentView()
        .accessibilityAction {
            // Handle action
        }
}
```

