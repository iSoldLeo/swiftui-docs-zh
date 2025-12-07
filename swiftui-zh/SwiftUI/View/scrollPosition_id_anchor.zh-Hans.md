--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollPosition(id:anchor:)

抓取时间：2025-12-02T17:40:14Z

---

# scrollPosition(id:anchor:)

**实例方法**

关联一个绑定，当此视图中的滚动视图滚动时，该绑定将被更新。

## 声明

```swift
nonisolated func scrollPosition(id: Binding<(some Hashable)?>, anchor: UnitPoint? = nil) -> some View

```

## 说明

将此修饰符与 `View/scrollTargetLayout()` 修饰符一起使用，可以确定当前滚动的视图的标识。当滚动视图滚动时，绑定将更新为最顶部视图的标识。

使用 `View/scrollTargetLayout()` 修饰符来配置包含滚动目标的布局。在以下示例中，当滚动视图滚动时，最顶层的 ItemView 将使用 scrolledID 绑定进行更新。

```swift
@Binding var items: [Item]
@Binding var scrolledID: Item.ID?

ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition(id: $scrolledID)
```

您可以写入绑定以滚动到具有指定标识的视图。

```swift
@Binding var items: [Item]
@Binding var scrolledID: Item.ID?

ScrollView {
    // ...
}
.scrollPosition(id: $scrolledID)
.toolbar {
    Button("Scroll to Top") {
        scrolledID = items.first
    }
}
```

当发生可能导致系统将其滚动出视图范围的事件时，SwiftUI 会尝试保持具有指定标识的视图可见。这些事件包括：

- 滚动视图内容的数据重新排序。

- 滚动视图的大小发生变化，例如在 macOS 上调整窗口大小或在 iOS 上旋转屏幕时。

- 滚动视图最初默认布局最顶层的视图，但绑定具有不同的视图标识。

您可以为此修饰符提供锚点，以：

- 影响系统选择哪个视图作为滚动视图滚动时更新绑定标识值的视图。

- 控制在写入新的绑定值时滚动到某个视图时的视图对齐方式。

例如，提供值 [bottom](../UnitPoint/bottom.zh-Hans.md) 将优先选择最底部的视图，并优先滚动到底部对齐的视图。

如果没有提供锚点，SwiftUI 在使用滚动位置以编程方式滚动到某个视图时，将滚动最小距离。

## 管理滚动位置

- **scrollPosition(_:anchor:)**：将绑定到滚动位置的滚动视图与该视图内的滚动视图关联起来。

- **defaultScrollAnchor(_:)**：关联一个锚点来控制默认情况下应渲染滚动视图内容的哪一部分。

- **defaultScrollAnchor(_:for:)**：关联一个锚点来控制滚动视图在特定情况下的位置。

- **ScrollAnchorRole**：定义滚动锚点角色的类型。

- **ScrollPosition**：定义滚动视图在其内容中滚动位置的语义类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollPosition(id:anchor:)
crawled: 2025-12-02T17:40:14Z
---

# scrollPosition(id:anchor:)

**Instance Method**

Associates a binding to be updated when a scroll view within this view scrolls.

## Declaration

```swift
nonisolated func scrollPosition(id: Binding<(some Hashable)?>, anchor: UnitPoint? = nil) -> some View

```

## Discussion

Use this modifier along with the `View/scrollTargetLayout()` modifier to know the identity of the view that is actively scrolled. As the scroll view scrolls, the binding will be updated with the identity of the leading-most / top-most view.

Use the `View/scrollTargetLayout()` modifier to configure which the layout that contains your scroll targets. In the following example, the top-most ItemView will update with the scrolledID binding as the scroll view scrolls.

```swift
@Binding var items: [Item]
@Binding var scrolledID: Item.ID?

ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition(id: $scrolledID)
```

You can write to the binding to scroll to the view with the provided identity.

```swift
@Binding var items: [Item]
@Binding var scrolledID: Item.ID?

ScrollView {
    // ...
}
.scrollPosition(id: $scrolledID)
.toolbar {
    Button("Scroll to Top") {
        scrolledID = items.first
    }
}
```

SwiftUI will attempt to keep the view with the identity specified in the provided binding visible when events occur that might cause it to be scrolled out of view by the system. Some examples of these include:

- The data backing the content of a scroll view is re-ordered.
- The size of the scroll view changes, like when a window is resized on macOS or during a rotation on iOS.
- The scroll view initially lays out it content defaulting to the top most view, but the binding has a different view’s identity.

You can provide an anchor to this modifier to both:

- Influence which view the system chooses as the view whose identity value will update the providing binding as the scroll view scrolls.
- Control the alignment of the view when scrolling to a view when writing a new binding value.

For example, providing a value of [bottom](../UnitPoint/bottom.zh-Hans.md) will prefer to have the bottom-most view chosen and prefer to scroll to views aligned to the bottom.

If no anchor has been provided, SwiftUI will scroll the minimal amount when using the scroll position to programmatically scroll to a view.

## Managing scroll position

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **ScrollAnchorRole**: A type defining the role of a scroll anchor.
- **ScrollPosition**: A type that defines the semantic position of where a scroll view is scrolled within its content.

