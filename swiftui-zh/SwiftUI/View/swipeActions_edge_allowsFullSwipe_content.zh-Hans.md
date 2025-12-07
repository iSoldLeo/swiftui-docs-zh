--- 来源：https://developer.apple.com/documentation/SwiftUI/View/swipeActions(edge:allowsFullSwipe:content:)

抓取时间：2025-11-30T20:49:55Z

---

# swipeActions(edge:allowsFullSwipe:content:)

**实例方法**

向列表的某一行添加自定义滑动操作。

## 声明

```swift
nonisolated func swipeActions<T>(edge: HorizontalEdge = .trailing, allowsFullSwipe: Bool = true, @ViewBuilder content: () -> T) -> some View where T : View

```

## 参数

- **edge**：要关联滑动操作的视图边缘。默认值为 [trailing](../HorizontalEdge/trailing.zh-Hans.md)。

- **allowsFullSwipe**：一个布尔值，指示完全滑动是否自动执行第一个操作。默认值为 `true`。

- **content**：滑动操作的内容。

## 讨论

使用此方法向作为列表行的视图添加滑动操作。指定滑动操作的起始位置（[HorizontalEdge](../HorizontalEdge.zh-Hans.md)），并使用 [Button](../Button.zh-Hans.md) 实例定义各个操作。例如，如果您有一个消息列表，您可以添加一个操作，用于在从列表顶部边缘滑动时将消息切换为未读状态；还可以添加一些操作，用于在从列表底部边缘滑动时删除或标记消息：

```swift
List {
    ForEach(store.messages) { message in
        MessageCell(message: message)
            .swipeActions(edge: .leading) {
                Button { store.toggleUnread(message) } label: {
                    if message.isUnread {
                        Label("Read", systemImage: "envelope.open")
                    } else {
                        Label("Unread", systemImage: "envelope.badge")
                    }
                }
            }
            .swipeActions(edge: .trailing) {
                Button(role: .destructive) {
                    store.delete(message)
                } label: {
                    Label("Delete", systemImage: "trash")
                }
                Button { store.flag(message) } label: {
                    Label("Flag", systemImage: "flag")
                }
            }
        }
    }
}
```

操作将按照您列出的顺序显示，从滑动操作的起始位置开始。在上面的示例中，“删除”操作出现在屏幕后缘附近：

对于滑动操作中出现的标签或图像，SwiftUI 会自动应用 [fill-swift.type.property](../SymbolVariants/fill-swift_type_property.zh-Hans.md) 符号变体，如上所示。

默认情况下，用户可以通过完全滑动来执行给定滑动方向的第一个操作。在上面的示例中，用户可以通过完全滑动来执行“切换未读”和“删除”操作。您可以通过将 `allowsFullSwipe` 参数设置为 `false` 来禁用此边缘行为。例如，您可以禁用前缘的完全滑动：

```swift
.swipeActions(edge: .leading, allowsFullSwipe: false) {
    Button { store.toggleUnread(message) } label: {
        if message.isUnread {
            Label("Read", systemImage: "envelope.open")
        } else {
            Label("Unread", systemImage: "envelope.badge")
        }
    }
}
```

当您使用 [ButtonRole](../ButtonRole.zh-Hans.md) 枚举中的值之一为按钮设置角色时，SwiftUI 会根据按钮的角色设置按钮样式。在上面的示例中，删除操作出现在 [red](../ShapeStyle/red.zh-Hans.md) 中，因为它具有 [destructive](../ButtonRole/destructive.zh-Hans.md) 角色。如果您想设置不同的颜色（例如，为了与应用的整体 UI 主题相匹配），请将 [tint(_:)](tint.zh-Hans.md) 修饰符添加到按钮：

```swift
MessageCell(message: message)
    .swipeActions(edge: .leading) {
        Button { store.toggleUnread(message) } label: {
            if message.isUnread {
                Label("Read", systemImage: "envelope.open")
            } else {
                Label("Unread", systemImage: "envelope.badge")
            }
        }
        .tint(.blue)
    }
    .swipeActions(edge: .trailing) {
        Button(role: .destructive) { store.delete(message) } label: {
            Label("Delete", systemImage: "trash")
        }
        Button { store.flag(message) } label: {
            Label("Flag", systemImage: "flag")
        }
        .tint(.orange)
    }
```

上述代码中的修改将切换未读状态的操作设为 [blue](../ShapeStyle/blue.zh-Hans.md)，标记操作设为 [orange](../ShapeStyle/orange.zh-Hans.md)：

添加滑动操作后，SwiftUI 不再自动生成在使用 [ForEach](../ForEach.zh-Hans.md) 实例上的 `ForEach/onDelete(perform:)` 方法时出现的删除操作。您需要负责在滑动操作中创建删除操作（如果需要）。

如果对同一列表行视图多次调用修饰符，则针对该边的操作会累积。

## 配置交互

- **selectionDisabled(_:)**：添加一个条件，用于控制用户是否可以选择此视图。

- **listRowHoverEffect(_:)**：请求包含此视图的列表行使用提供的悬停效果。

- **listRowHoverEffectDisabled(_:)**：请求禁用包含此视图的列表行的悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/swipeActions(edge:allowsFullSwipe:content:)
crawled: 2025-11-30T20:49:55Z
---

# swipeActions(edge:allowsFullSwipe:content:)

**Instance Method**

Adds custom swipe actions to a row in a list.

## Declaration

```swift
nonisolated func swipeActions<T>(edge: HorizontalEdge = .trailing, allowsFullSwipe: Bool = true, @ViewBuilder content: () -> T) -> some View where T : View

```

## Parameters

- **edge**: The edge of the view to associate the swipe actions with. The default is [trailing](../HorizontalEdge/trailing.zh-Hans.md).
- **allowsFullSwipe**: A Boolean value that indicates whether a full swipe automatically performs the first action. The default is `true`.
- **content**: The content of the swipe actions.

## Discussion

Use this method to add swipe actions to a view that acts as a row in a list. Indicate the [HorizontalEdge](../HorizontalEdge.zh-Hans.md) where the swipe action originates, and define individual actions with [Button](../Button.zh-Hans.md) instances. For example, if you have a list of messages, you can add an action to toggle a message as unread on a swipe from the leading edge, and actions to delete or flag messages on a trailing edge swipe:

```swift
List {
    ForEach(store.messages) { message in
        MessageCell(message: message)
            .swipeActions(edge: .leading) {
                Button { store.toggleUnread(message) } label: {
                    if message.isUnread {
                        Label("Read", systemImage: "envelope.open")
                    } else {
                        Label("Unread", systemImage: "envelope.badge")
                    }
                }
            }
            .swipeActions(edge: .trailing) {
                Button(role: .destructive) {
                    store.delete(message)
                } label: {
                    Label("Delete", systemImage: "trash")
                }
                Button { store.flag(message) } label: {
                    Label("Flag", systemImage: "flag")
                }
            }
        }
    }
}
```

Actions appear in the order you list them, starting from the swipe’s originating edge. In the example above, the Delete action appears closest to the screen’s trailing edge:



For labels or images that appear in swipe actions, SwiftUI automatically applies the [fill-swift.type.property](../SymbolVariants/fill-swift_type_property.zh-Hans.md) symbol variant, as shown above.

By default, the user can perform the first action for a given swipe direction with a full swipe. For the example above, the user can perform both the toggle unread and delete actions with full swipes. You can opt out of this behavior for an edge by setting the `allowsFullSwipe` parameter to `false`. For example, you can disable the full swipe on the leading edge:

```swift
.swipeActions(edge: .leading, allowsFullSwipe: false) {
    Button { store.toggleUnread(message) } label: {
        if message.isUnread {
            Label("Read", systemImage: "envelope.open")
        } else {
            Label("Unread", systemImage: "envelope.badge")
        }
    }
}
```

When you set a role for a button using one of the values from the [ButtonRole](../ButtonRole.zh-Hans.md) enumeration, SwiftUI styles the button according to its role. In the example above, the delete action appears in [red](../ShapeStyle/red.zh-Hans.md) because it has the [destructive](../ButtonRole/destructive.zh-Hans.md) role. If you want to set a different color — for example, to match the overall theme of your app’s UI — add the [tint(_:)](tint.zh-Hans.md) modifier to the button:

```swift
MessageCell(message: message)
    .swipeActions(edge: .leading) {
        Button { store.toggleUnread(message) } label: {
            if message.isUnread {
                Label("Read", systemImage: "envelope.open")
            } else {
                Label("Unread", systemImage: "envelope.badge")
            }
        }
        .tint(.blue)
    }
    .swipeActions(edge: .trailing) {
        Button(role: .destructive) { store.delete(message) } label: {
            Label("Delete", systemImage: "trash")
        }
        Button { store.flag(message) } label: {
            Label("Flag", systemImage: "flag")
        }
        .tint(.orange)
    }
```

The modifications in the code above make the toggle unread action [blue](../ShapeStyle/blue.zh-Hans.md) and the flag action [orange](../ShapeStyle/orange.zh-Hans.md):



When you add swipe actions, SwiftUI no longer synthesizes the Delete actions that otherwise appear when using the `ForEach/onDelete(perform:)` method on a [ForEach](../ForEach.zh-Hans.md) instance. You become responsible for creating a Delete action, if appropriate, among your swipe actions.

Actions accumulate for a given edge if you call the modifier multiple times on the same list row view.

## Configuring interaction

- **selectionDisabled(_:)**: Adds a condition that controls whether users can select this view.
- **listRowHoverEffect(_:)**: Requests that the containing list row use the provided hover effect.
- **listRowHoverEffectDisabled(_:)**: Requests that the containing list row have its hover effect disabled.

