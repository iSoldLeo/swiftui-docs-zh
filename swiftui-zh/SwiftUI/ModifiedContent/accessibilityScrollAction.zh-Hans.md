---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityScrollAction(_:)
抓取时间： 2025-11-30T21:32:01Z
---

# accessibilityScrollAction(_:)

**实例方法**

为视图添加辅助滚动操作。该操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

### 声明

```swift
nonisolated func accessibilityScrollAction(_ handler: @escaping (Edge) -> Void) -> ModifiedContent<Content, Modifier>
```

## 讨论

例如，可以在视图中添加滚动操作来触发刷新。

```swift
var body: some View {
    ScrollView {
        ContentView()
    }
    .accessibilityScrollAction { edge in
        if edge == .top {
            // Refresh content
        }
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityScrollAction(_:)
crawled: 2025-11-30T21:32:01Z
---

# accessibilityScrollAction(_:)

**Instance Method**

Adds an accessibility scroll action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityScrollAction(_ handler: @escaping (Edge) -> Void) -> ModifiedContent<Content, Modifier>
```

## Discussion

For example, this is how a scroll action to trigger a refresh could be added to a view.

```swift
var body: some View {
    ScrollView {
        ContentView()
    }
    .accessibilityScrollAction { edge in
        if edge == .top {
            // Refresh content
        }
    }
}
```

