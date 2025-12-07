--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityScrollAction(_:)

抓取时间：2025-12-02T17:43:52Z

---

# accessibilityScrollAction(_:)

**实例方法**

向视图添加辅助功能滚动操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

## 声明

```swift
nonisolated func accessibilityScrollAction(_ handler: @escaping (Edge) -> Void) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 讨论

例如，以下是如何向视图添加触发刷新的滚动操作。

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

## 向视图添加操作

- **accessibilityAction(_:_:)**：向视图添加辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityActions(_:)**：向视图添加多个辅助功能操作。

- **accessibilityAction(named:_:)**：向视图添加一个辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(action:label:)**：向视图添加一个辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityAction(intent:label:)**：向视图添加一个由 `label` 的内容标记的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(_:intent:)**：向视图添加一个代表 `actionKind` 的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAction(named:intent:)**：向视图添加一个标记为 `name` 的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。执行该操作时，将调用 `intent`。

- **accessibilityAdjustableAction(_:)**：向视图添加一个可调节的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用该操作与视图进行交互。

- **accessibilityActions(category:_:)**：为视图添加多个具有特定类别的辅助功能操作。操作允许 VoiceOver 等辅助技术通过调用操作与视图交互，并按类别分组。当多个具有相同类别的操作修饰符应用于视图时，这些操作将合并在一起。

- **AccessibilityActionKind**：定义可用辅助功能操作类型的结构。

- **AccessibilityAdjustmentDirection**：进行辅助功能调整时使用的方向指示器。

- **AccessibilityActionCategory**：指定由系统提供和命名的辅助功能操作类别。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityScrollAction(_:)
crawled: 2025-12-02T17:43:52Z
---

# accessibilityScrollAction(_:)

**Instance Method**

Adds an accessibility scroll action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.

## Declaration

```swift
nonisolated func accessibilityScrollAction(_ handler: @escaping (Edge) -> Void) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
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

## Adding actions to views

- **accessibilityAction(_:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(_:)**: Adds multiple accessibility actions to the view.
- **accessibilityAction(named:_:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(action:label:)**: Adds an accessibility action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityAction(intent:label:)**: Adds an accessibility action labeled by the contents of `label` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(_:intent:)**: Adds an accessibility action representing `actionKind` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAction(named:intent:)**: Adds an accessibility action labeled `name` to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action. When the action is performed, the `intent` will be invoked.
- **accessibilityAdjustableAction(_:)**: Adds an accessibility adjustable action to the view. Actions allow assistive technologies, such as the VoiceOver, to interact with the view by invoking the action.
- **accessibilityActions(category:_:)**: Adds multiple accessibility actions to the view with a specific category. Actions allow assistive technologies, such as VoiceOver, to interact with the view by invoking the action and are grouped by their category. When multiple action modifiers with an equal category are applied to the view, the actions are combined together.
- **AccessibilityActionKind**: The structure that defines the kinds of available accessibility actions.
- **AccessibilityAdjustmentDirection**: A directional indicator you use when making an accessibility adjustment.
- **AccessibilityActionCategory**: Designates an accessibility action category that is provided and named by the system.

