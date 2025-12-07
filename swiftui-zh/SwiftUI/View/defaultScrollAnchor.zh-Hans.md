--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultScrollAnchor(_:)

抓取时间：2025-12-02T17:40:15Z

---

# defaultScrollAnchor(_:)

**实例方法**

关联一个锚点，用于控制滚动视图内容的默认渲染部分。

## 声明

```swift
nonisolated func defaultScrollAnchor(_ anchor: UnitPoint?) -> some View

```

## 说明

使用此修饰符可以指定一个锚点，用于控制滚动视图内容的初始可见部分以及滚动视图如何处理内容大小的变化。

提供值 `UnitPoint/center`` to have the scroll view start in the center of its content when a scroll view is scrollable in both axes.

⟦CB_0002⟧

Provide a value of `UnitPoint/bottom`，可使滚动视图在垂直方向滚动时从内容底部开始滚动。

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
```

用户可以滚动到偏离初始定义的滚动位置。当滚动视图的内容大小发生变化时，系统会参考锚点来确定如何重新定位内容。

## 管理滚动位置

- **scrollPosition(_:anchor:)**：将滚动位置绑定到此视图内的滚动视图。

- **scrollPosition(id:anchor:)**：将要更新的绑定关联到此视图内的滚动视图。

- **defaultScrollAnchor(_:for:)**：将锚点关联到特定情况下用于控制滚动视图位置的锚点。

- **ScrollAnchorRole**：定义滚动锚点作用的类型。

- **ScrollPosition**：定义滚动视图在其内容中滚动的语义位置的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultScrollAnchor(_:)
crawled: 2025-12-02T17:40:15Z
---

# defaultScrollAnchor(_:)

**Instance Method**

Associates an anchor to control which part of the scroll view’s content should be rendered by default.

## Declaration

```swift
nonisolated func defaultScrollAnchor(_ anchor: UnitPoint?) -> some View

```

## Discussion

Use this modifier to specify an anchor to control both which part of the scroll view’s content should be visible initially and how the scroll view handles content size changes.

Provide a value of `UnitPoint/center`` to have the scroll view start in the center of its content when a scroll view is scrollable in both axes.

```swift
ScrollView([.horizontal, .vertical]) {
    // initially centered content
}
.defaultScrollAnchor(.center)
```

Provide a value of `UnitPoint/bottom` to have the scroll view start at the bottom of its content when scrollable in the vertical axis.

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
```

The user may scroll away from the initial defined scroll position. When the content size of the scroll view changes, it may consult the anchor to know how to reposition the content.

## Managing scroll position

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **ScrollAnchorRole**: A type defining the role of a scroll anchor.
- **ScrollPosition**: A type that defines the semantic position of where a scroll view is scrolled within its content.

