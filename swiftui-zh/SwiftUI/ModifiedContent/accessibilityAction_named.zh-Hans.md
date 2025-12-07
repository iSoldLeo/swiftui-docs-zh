---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(named:_:)
抓取时间：2025-11-30T21:31:41Z
---

# accessibilityAction(named:_:)

**实例方法**

为视图添加辅助操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图进行交互。

### 声明

```swift
nonisolated func accessibilityAction(named name: Text, _ handler: @escaping () -> Void) -> ModifiedContent<Content, Modifier>
```

## 讨论

例如，可以在视图中添加编写新邮件的自定义操作。

```swift
var body: some View {
    ContentView()
        .accessibilityAction(named: Text("New Message")) {
            // Handle action
        }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAction(named:_:)
crawled: 2025-11-30T21:31:41Z
---

# accessibilityAction(named:_:)

**Instance Method**

Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityAction(named name: Text, _ handler: @escaping () -> Void) -> ModifiedContent<Content, Modifier>
```

## Discussion

For example, this is how a custom action to compose a new email could be added to a view.

```swift
var body: some View {
    ContentView()
        .accessibilityAction(named: Text("New Message")) {
            // Handle action
        }
}
```

