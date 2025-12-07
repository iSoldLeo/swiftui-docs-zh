---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAdjustableAction(_:)
抓取时间： 2025-11-30T21:31:45Z
---

# accessibilityAdjustableAction(_:)

**实例方法**

向视图添加可调整辅助功能的操作。该操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

### 声明

```swift
nonisolated func accessibilityAdjustableAction(_ handler: @escaping (AccessibilityAdjustmentDirection) -> Void) -> ModifiedContent<Content, Modifier>
```

## 讨论

例如，可以在视图中添加一个可调整的操作来浏览页面。

```swift
var body: some View {
    PageControl()
        .accessibilityAdjustableAction { direction in
            switch direction {
            case .increment:
                // Go to next page
            case .decrement:
                // Go to previous page
            }
        }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityAdjustableAction(_:)
crawled: 2025-11-30T21:31:45Z
---

# accessibilityAdjustableAction(_:)

**Instance Method**

Adds an accessibility adjustable action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityAdjustableAction(_ handler: @escaping (AccessibilityAdjustmentDirection) -> Void) -> ModifiedContent<Content, Modifier>
```

## Discussion

For example, this is how an adjustable action to navigate through pages could be added to a view.

```swift
var body: some View {
    PageControl()
        .accessibilityAdjustableAction { direction in
            switch direction {
            case .increment:
                // Go to next page
            case .decrement:
                // Go to previous page
            }
        }
}
```

