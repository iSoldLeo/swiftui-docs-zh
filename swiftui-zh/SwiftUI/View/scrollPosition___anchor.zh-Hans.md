--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollPosition(_:anchor:)

抓取时间：2025-12-02T17:40:14Z

---

# scrollPosition(_:anchor:)

**实例方法**

将滚动位置绑定到此视图中的滚动视图。

## 声明

```swift
nonisolated func scrollPosition(_ position: Binding<ScrollPosition>, anchor: UnitPoint? = nil) -> some View

```

## 讨论

使用此修饰符控制滚动视图的位置。您可以使用 [ScrollPosition](../ScrollPosition.zh-Hans.md) 类型以多种方式滚动：

- 滚动到具有指定标识的视图

- 滚动到特定偏移量

- 滚动到边缘

您可以使用指定的视图标识类型创建滚动位置

```swift
@State private var position
    = ScrollPosition(idType: MyItem.ID.self)
```

SwiftUI 将结合滚动视图的滚动目标布局中的视图，以编程方式滚动到这些视图，并在用户滚动时更新 [viewID](../ScrollPosition/viewID.zh-Hans.md) 属性。使用 `View/scrollTargetLayout()` 修饰符来配置包含滚动目标的布局。

当滚动到具有标识符的视图时，SwiftUI 会将位置更新为滚动视图可见区域内滚动到的最顶层视图的值。

在以下示例中，位置绑定将随着滚动视图的滚动而更新，以反映最顶层的 ItemView。

```swift
@Binding var items: [MyItem]
@State private var position: ScrollPosition
    = .init(idType: MyItem.ID.self)

ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition($position)
```

然后，您可以使用 [viewID(type:)](../ScrollPosition/viewID_type.zh-Hans.md) 查询当前滚动的 ID。

```swift
let viewID: MyItem.ID = position.viewID(type: MyItem.ID.self)
```

虽然大多数用例会使用基于视图标识的滚动，但您也可以使用滚动位置类型来滚动到偏移量或边缘。例如，您可以通过指定边缘来创建一个滚动到滚动视图底部的按钮。

```swift
Button("Scroll to bottom") {
    position.scrollTo(edge: .bottom)
}
```

配置滚动位置时，SwiftUI 会尝试保持该位置稳定。对于边缘，这意味着即使内容大小发生变化，顶部对齐的滚动视图也会保持滚动到顶部。对于点，SwiftUI 不会尝试在内容大小发生变化时保持该偏移量滚动，也不会在内容大小发生变化时更新到新的偏移量。

对于视图标识位置，SwiftUI 会尝试在发生可能导致系统将其滚动出屏幕的事件时，保持绑定中指定的标识对应的视图可见。这些事件包括：

- 滚动视图内容的数据重新排序。

- 滚动视图的大小发生变化，例如在 macOS 上调整窗口大小或在 iOS 上旋转屏幕。

- 滚动视图最初默认布局最顶层的视图，但绑定中指定的标识是不同的视图。

您可以为基于视图标识的位置提供锚点，以：

- 影响系统在滚动视图滚动时选择哪个视图作为标识值更新绑定的视图。

- 控制在写入新的绑定值时滚动到某个视图时的视图对齐方式。

在下面的示例中，将选择最底层的视图来更新位置绑定。

```swift
ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition($position, anchor: .bottom)
```

例如，提供值 [bottom](../UnitPoint/bottom.zh-Hans.md) 将优先选择最底部的视图，并优先滚动到与底部对齐的视图。

## 管理滚动位置

- **scrollPosition(id:anchor:)**：关联一个绑定，当此视图内的滚动视图滚动时，该绑定将被更新。

- **defaultScrollAnchor(_:)**：关联一个锚点，用于控制默认情况下应渲染滚动视图内容的哪一部分。

- **defaultScrollAnchor(_:for:)**：关联一个锚点，用于控制滚动视图在特定情况下的位置。

- **ScrollAnchorRole**：定义滚动锚点角色的类型。

- **ScrollPosition**：定义滚动视图在其内容中滚动的语义位置的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollPosition(_:anchor:)
crawled: 2025-12-02T17:40:14Z
---

# scrollPosition(_:anchor:)

**Instance Method**

Associates a binding to a scroll position with a scroll view within this view.

## Declaration

```swift
nonisolated func scrollPosition(_ position: Binding<ScrollPosition>, anchor: UnitPoint? = nil) -> some View

```

## Discussion

Use this modifier to control where a scroll view is positioned. You can use the [ScrollPosition](../ScrollPosition.zh-Hans.md) type to scroll in a variety of ways:

- scroll to a view with a provided identity
- scroll to a concrete offset
- scroll to an edge

You can create a scroll position with a specified view identity type

```swift
@State private var position
    = ScrollPosition(idType: MyItem.ID.self)
```

SwiftUI will use that along with the views in the scroll view’s scroll target layout to programmatically scroll to those views and to update the [viewID](../ScrollPosition/viewID.zh-Hans.md) property as the user scrolls. Use the `View/scrollTargetLayout()` modifier to configure which the layout that contains your scroll targets.

When scrolling to a view with an identifier, SwiftUI will update the position with the value of the top-most view scrolled within the visible region of the scroll view.

In the following example, the position binding will update to reflect the top-most ItemView as the scroll view scrolls.

```swift
@Binding var items: [MyItem]
@State private var position: ScrollPosition
    = .init(idType: MyItem.ID.self)

ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition($position)
```

You can then query the currently scrolled id by using the [viewID(type:)](../ScrollPosition/viewID_type.zh-Hans.md).

```swift
let viewID: MyItem.ID = position.viewID(type: MyItem.ID.self)
```

While most use cases will use view identity based scrolling, you can also use the scroll position type to scroll to offsets or edges. For example, you can create a button that scrolls to the bottom of the scroll view by specifying an edge.

```swift
Button("Scroll to bottom") {
    position.scrollTo(edge: .bottom)
}
```

When configuring a scroll position, SwiftUI will attempt to keep that position stable. For an edge, that means keeping a top aligned scroll view scrolled to the top if the content size changes. For a point, SwiftUI won’t attempt to keep that exact offset scrolled when the content size changes nor will it update to a new offset when that changes.

For view identity positions, SwiftUI will attempt to keep the view with the identity specified in the provided binding visible when events occur that might cause it to be scrolled out of view by the system. Some examples of these include:

- The data backing the content of a scroll view is re-ordered.
- The size of the scroll view changes, like when a window is resized on macOS or during a rotation on iOS.
- The scroll view initially lays out it content defaulting to the top most view, but the binding has a different view’s identity.

You can provide an anchor to a view identity based position to:

- Influence which view the system chooses as the view whose identity value will update the providing binding as the scroll view scrolls.
- Control the alignment of the view when scrolling to a view when writing a new binding value.

In the example below, the bottom most view will be chosen to update the position binding with.

```swift
ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition($position, anchor: .bottom)
```

For example, providing a value of [bottom](../UnitPoint/bottom.zh-Hans.md) will prefer to have the bottom-most view chosen and prefer to scroll to views aligned to the bottom.

## Managing scroll position

- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **ScrollAnchorRole**: A type defining the role of a scroll anchor.
- **ScrollPosition**: A type that defines the semantic position of where a scroll view is scrolled within its content.

