---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/swipeActions(edge:allowsFullSwipe:content:)
抓取时间：2025-12-01T10:50:53Z


# swipeActions(edge:allowsFullSwipe:content:)

**实例方法**

在标签视图中为标签页添加自定义轻扫操作。

## 声明

```swift
nonisolated func swipeActions<T>(edge: HorizontalEdge = .trailing, allowsFullSwipe: Bool = true, @ViewBuilder content: () -> T) -> some TabContent<Self.TabValue> where T : View

```

## 参数

- **edge**：要关联轻扫操作的视图边缘。默认值为 [trailing](../HorizontalEdge/trailing.zh-Hans.md)。
- **allowsFullSwipe**：布尔值，用于指示完全轻扫是否自动执行第一个操作。默认值为 `true`。
- **content**：轻扫操作的内容。

## 讨论

使用此方法可将轻扫操作添加到视图中，该视图在标签页侧边栏中充当一行。指出轻扫操作的源头[HorizontalEdge](../HorizontalEdge.zh-Hans.md)，并用[Button](../Button.zh-Hans.md)实例定义单个操作。例如，如果你有一组信息类别，你可以添加一个动作，在从前缘轻扫时将类别切换为未读，以及在后缘轻扫时隐藏或标记类别：

```swift
TabView {
     TabSection("Messages") {
         ForEach(store.messageCategories) { category in
             Tab(category.title, image: category.image)
                 .swipeActions(edge: .leading) {
                     Button { store.toggleUnread(category) } label: {
                         if category.isUnread {
                             Label("Read", systemImage: "envelope.open")
                         } else {
                             Label("Unread", systemImage: "envelope.badge")
                         }
                     }
                 }
                 .swipeActions(edge: .trailing) {
                     Button(role: .destructive) {
                         store.hide(category)
                     } label: {
                         Label("Remove", systemImage: "trash")
                     }
                     Button { store.flag(category) } label: {
                         Label("Flag", systemImage: "flag")
                     }
                 }
             }
         }
     }
}
```

操作会按照你列出的顺序出现，从轻扫的起始边缘开始。在上面的示例中，删除操作显示在最靠近屏幕后缘的位置。

对于出现在轻扫操作中的标签或图像，SwiftUI 会自动应用[fill-swift.type.property](../SymbolVariants/fill-swift_type_property.zh-Hans.md) 符号变体，如上图所示。

默认情况下，用户可以通过完全轻扫来执行给定轻扫方向的第一个操作。在上面的示例中，用户可以通过完全轻扫来执行切换未读和删除操作。通过将 `allowsFullSwipe`参数设置为 `false`，您可以选择不对边缘执行此行为。例如，您可以禁用前缘的完全轻扫：

```swift
.swipeActions(edge: .leading, allowsFullSwipe: false) {
    Button { store.toggleUnread(category) } label: {
        if category.isUnread {
            Label("Read", systemImage: "envelope.open")
        } else {
            Label("Unread", systemImage: "envelope.badge")
        }
    }
}
```

当您使用 [ButtonRole](../ButtonRole.zh-Hans.md) 枚举中的某个值为按钮设置角色时，SwiftUI 将根据其角色为按钮设计样式。在上面的示例中，删除操作显示在 [red](../ShapeStyle/red.zh-Hans.md) 中，因为它具有 [destructive](../ButtonRole/destructive.zh-Hans.md) 角色。如果您想设置不同的颜色（例如，为了与应用程序 UI 的整体主题相匹配），请在[tint(_:)](../View/tint.zh-Hans.md) 按钮上添加⟦修饰符：

```swift
.swipeActions(edge: .leading) {
    Button { store.toggleUnread(category) } label: {
        if category.isUnread {
            Label("Read", systemImage: "envelope.open")
        } else {
            Label("Unread", systemImage: "envelope.badge")
        }
    }
    .tint(.blue)
}
.swipeActions(edge: .trailing) {
    Button(role: .destructive) { store.hide(category) } label: {
        Label("Hide", systemImage: "trash")
    }
    Button { store.flag(category) } label: {
        Label("Flag", systemImage: "flag")
    }
    .tint(.orange)
}
```

上述代码中的修改使切换未读操作 [blue](../ShapeStyle/blue.zh-Hans.md) 和标记操作 [orange](../ShapeStyle/orange.zh-Hans.md)：

如果在同一标签页上多次调用修改器，则给定边缘的操作会累加。


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/swipeActions(edge:allowsFullSwipe:content:)
crawled: 2025-12-01T10:50:53Z
---

# swipeActions(edge:allowsFullSwipe:content:)

**Instance Method**

Adds custom swipe actions to a tab in a tab view.

## Declaration

```swift
nonisolated func swipeActions<T>(edge: HorizontalEdge = .trailing, allowsFullSwipe: Bool = true, @ViewBuilder content: () -> T) -> some TabContent<Self.TabValue> where T : View

```

## Parameters

- **edge**: The edge of the view to associate the swipe actions with. The default is [trailing](../HorizontalEdge/trailing.zh-Hans.md).
- **allowsFullSwipe**: A Boolean value that indicates whether a full swipe automatically performs the first action. The default is `true`.
- **content**: The content of the swipe actions.

## Discussion

Use this method to add swipe actions to a view that acts as a row in the tab sidebar. Indicate the [HorizontalEdge](../HorizontalEdge.zh-Hans.md) where the swipe action originates, and define individual actions with [Button](../Button.zh-Hans.md) instances. For example, if you have a group of message categories, you can add an action to toggle a category as unread on a swipe from the leading edge, and actions to hide or flag categories on a trailing edge swipe:

```swift
TabView {
     TabSection("Messages") {
         ForEach(store.messageCategories) { category in
             Tab(category.title, image: category.image)
                 .swipeActions(edge: .leading) {
                     Button { store.toggleUnread(category) } label: {
                         if category.isUnread {
                             Label("Read", systemImage: "envelope.open")
                         } else {
                             Label("Unread", systemImage: "envelope.badge")
                         }
                     }
                 }
                 .swipeActions(edge: .trailing) {
                     Button(role: .destructive) {
                         store.hide(category)
                     } label: {
                         Label("Remove", systemImage: "trash")
                     }
                     Button { store.flag(category) } label: {
                         Label("Flag", systemImage: "flag")
                     }
                 }
             }
         }
     }
}
```

Actions appear in the order you list them, starting from the swipe’s originating edge. In the example above, the Delete action appears closest to the screen’s trailing edge.

For labels or images that appear in swipe actions, SwiftUI automatically applies the [fill-swift.type.property](../SymbolVariants/fill-swift_type_property.zh-Hans.md) symbol variant, as shown above.

By default, the user can perform the first action for a given swipe direction with a full swipe. For the example above, the user can perform both the toggle unread and delete actions with full swipes. You can opt out of this behavior for an edge by setting the `allowsFullSwipe` parameter to `false`. For example, you can disable the full swipe on the leading edge:

```swift
.swipeActions(edge: .leading, allowsFullSwipe: false) {
    Button { store.toggleUnread(category) } label: {
        if category.isUnread {
            Label("Read", systemImage: "envelope.open")
        } else {
            Label("Unread", systemImage: "envelope.badge")
        }
    }
}
```

When you set a role for a button using one of the values from the [ButtonRole](../ButtonRole.zh-Hans.md) enumeration, SwiftUI styles the button according to its role. In the example above, the delete action appears in [red](../ShapeStyle/red.zh-Hans.md) because it has the [destructive](../ButtonRole/destructive.zh-Hans.md) role. If you want to set a different color — for example, to match the overall theme of your app’s UI — add the [tint(_:)](../View/tint.zh-Hans.md) modifier to the button:

```swift
.swipeActions(edge: .leading) {
    Button { store.toggleUnread(category) } label: {
        if category.isUnread {
            Label("Read", systemImage: "envelope.open")
        } else {
            Label("Unread", systemImage: "envelope.badge")
        }
    }
    .tint(.blue)
}
.swipeActions(edge: .trailing) {
    Button(role: .destructive) { store.hide(category) } label: {
        Label("Hide", systemImage: "trash")
    }
    Button { store.flag(category) } label: {
        Label("Flag", systemImage: "flag")
    }
    .tint(.orange)
}
```

The modifications in the code above make the toggle unread action [blue](../ShapeStyle/blue.zh-Hans.md) and the flag action [orange](../ShapeStyle/orange.zh-Hans.md):

Actions accumulate for a given edge if you call the modifier multiple times on the same tab.

