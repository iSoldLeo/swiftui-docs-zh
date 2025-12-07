--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultScrollAnchor(_:for:)

抓取时间：2025-11-30T21:25:20Z

---

# defaultScrollAnchor(_:for:)

**实例方法**

关联一个锚点，用于在特定情况下控制滚动视图的位置。

## 声明

```swift
nonisolated func defaultScrollAnchor(_ anchor: UnitPoint?, for role: ScrollAnchorRole) -> some View

```

## 讨论

您可以使用 [defaultScrollAnchor(_:)](defaultScrollAnchor.zh-Hans.md) 修饰符将 [UnitPoint](../UnitPoint.zh-Hans.md) 与 [ScrollView](../ScrollView.zh-Hans.md) 关联起来。默认情况下，系统使用此点来控制各种行为，包括：

- 滚动视图的初始滚动位置

- 滚动视图如何处理内容大小或容器大小的变化

- 滚动视图如何对齐小于其容器大小的内容

您可以通过为这些不同情况分配不同的单位点来进一步自定义此行为。

例如，您可以使用 [defaultScrollAnchor(_:)](defaultScrollAnchor.zh-Hans.md) 修饰符，将 [bottom](../UnitPoint/bottom.zh-Hans.md) 作为所有情况的锚点值，然后通过为某些情况提供不同的值来选择不应用此行为。

```swift
@Binding var items: [Item]
@Binding var scrolledID: Item.ID?

ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
}
.defaultScrollAnchor(.bottom)
.defaultScrollAnchor(.topLeading, for: .alignment)
```

## 管理滚动位置

- **scrollPosition(_:anchor:)**：将一个绑定到此视图内滚动视图的滚动位置。

- **scrollPosition(id:anchor:)**：将一个绑定关联到此视图内滚动视图滚动时要更新的位置。

- **defaultScrollAnchor(_:)**：关联一个锚点，用于控制默认情况下应渲染滚动视图内容的哪一部分。

- **ScrollAnchorRole**：定义滚动锚点角色的类型。

- **ScrollPosition**：定义滚动视图在其内容中滚动的语义位置的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultScrollAnchor(_:for:)
crawled: 2025-11-30T21:25:20Z
---

# defaultScrollAnchor(_:for:)

**Instance Method**

Associates an anchor to control the position of a scroll view in a particular circumstance.

## Declaration

```swift
nonisolated func defaultScrollAnchor(_ anchor: UnitPoint?, for role: ScrollAnchorRole) -> some View

```

## Discussion

You can associate a [UnitPoint](../UnitPoint.zh-Hans.md) to a [ScrollView](../ScrollView.zh-Hans.md) using the [defaultScrollAnchor(_:)](defaultScrollAnchor.zh-Hans.md) modifier. By default, the system uses this point for different kinds of behaviors including:

- Where the scroll view should initially be scrolled
- How the scroll view should handle content size or container size changes
- How the scroll view should align content smaller than its container size

You can further customize this behavior by assigning different unit points for these different cases.

For example, you can use the [defaultScrollAnchor(_:)](defaultScrollAnchor.zh-Hans.md) modifier to provide a value of [bottom](../UnitPoint/bottom.zh-Hans.md) as the anchor for all cases and then opt out of certain cases by providing a different value for them.

```swift
@Binding var items: [Item]
@Binding var scrolledID: Item.ID?

ScrollView {
    LazyVStack {
        ForEach(items) { item in
            ItemView(item)
        }
    }
}
.defaultScrollAnchor(.bottom)
.defaultScrollAnchor(.topLeading, for: .alignment)
```

## Managing scroll position

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **ScrollAnchorRole**: A type defining the role of a scroll anchor.
- **ScrollPosition**: A type that defines the semantic position of where a scroll view is scrolled within its content.

