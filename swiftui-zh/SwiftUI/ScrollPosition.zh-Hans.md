--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollPosition
抓取时间：2025-12-02T17:40:18Z

---

# ScrollPosition

**Structure**

定义滚动视图在其内容中滚动位置的语义类型。

## 声明

```swift
struct ScrollPosition
```

## 概述

将此类型与 `View/scrollPosition(_:)` 修饰符一起使用，以控制滚动视图的位置。您可以使用此类型以多种方式滚动：

- 滚动到具有指定标识的视图

- 滚动到特定偏移量

- 滚动到边缘

您可以创建具有指定视图标识类型的滚动位置

```swift
@State private var position = ScrollPosition(idType: MyItem.ID.self)
```

SwiftUI 将使用此标识以及滚动视图的滚动目标布局中的视图，以编程方式滚动到这些视图，并在用户滚动时更新 [viewID](ScrollPosition/viewID.zh-Hans.md) 属性。使用 `View/scrollTargetLayout()` 修饰符来配置包含滚动目标的布局。

当滚动到具有标识符的视图时，SwiftUI 会使用滚动视图可见区域内滚动到的最顶层视图的值来更新位置。

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
.scrollPosition($scrolledID)
```

然后，您可以使用 [viewID(type:)](ScrollPosition/viewID_type.zh-Hans.md) 查询当前滚动的 ID。

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
.scrollPosition($scrolledID, anchor: .bottom)
```

例如，提供值 [bottom](UnitPoint/bottom.zh-Hans.md) 将优先选择最底部的视图，并优先滚动到与底部对齐的视图。

如果没有提供锚点，SwiftUI 在使用滚动位置以编程方式滚动到视图时，将滚动最小距离。

## 初始化器

- **init(id:anchor:)**：创建一个新的滚动位置，滚动到具有指定标识值的视图。

- **init(idType:)**：创建一个新的自动滚动位置。

- **init(idType:edge:)**：创建一个新的滚动位置，滚动到指定的边缘。

- **init(idType:point:)**：创建一个新的滚动位置，滚动到指定的位置。

- **init(idType:x:)**：创建一个新的滚动位置，滚动到指定的 y 值。

- **init(idType:x:y:)**：创建一个新的滚动位置，滚动到指定的 x 值。

- **init(idType:y:)**：创建一个新的滚动位置，滚动到指定的 y 值。

## 实例属性

- **edge**：如果已配置为滚动视图的定位边缘，则此属性为滚动视图的定位边缘。

- **isPositionedByUser**：滚动视图是否由用户定位。

- **point**：如果已配置为滚动视图的定位点，则此属性为滚动视图的定位点。

- **viewID**：如果滚动视图配置为位于该位置，或者用户滚动浏览过 ID 匹配的视图，则返回滚动视图中当前视图的已擦除类型 ID。

- **x**：如果滚动视图配置为位于该位置，则返回滚动视图的 x 坐标值。

- **y**：如果滚动视图配置为位于该位置，则返回滚动视图的 y 坐标值。

## 实例方法

- **scrollTo(edge:)**：将滚动视图滚动到您指定的边缘。

- **scrollTo(id:anchor:)**：将滚动视图滚动到您指定的具有标识值和锚点的视图。

- **scrollTo(point:)**：将滚动视图滚动到您指定的点。

- **scrollTo(x:)**：将滚动视图的位置滚动到您提供的 x 值。

- **scrollTo(x:y:)**：将滚动视图的位置滚动到您提供的 x 和 y 值。

- **scrollTo(y:)**：将滚动视图的位置滚动到您提供的 y 值。

- **viewID(type:)**：如果滚动视图已配置为位于该位置，或者用户已滚动到 ID 匹配类型的视图之后，则返回该视图中当前视图的 ID。

## 管理滚动位置

- **scrollPosition(_:anchor:)**：将滚动位置绑定到此视图中的滚动视图。

- **scrollPosition(id:anchor:)**：将要更新的绑定关联到此视图中的滚动视图滚动时。

- **defaultScrollAnchor(_:)**：关联一个锚点，用于控制默认情况下应渲染滚动视图内容的哪一部分。

- **defaultScrollAnchor(_:for:)**：关联一个锚点，用于控制滚动视图在特定情况下的位置。

- **ScrollAnchorRole**：定义滚动锚点角色的类型。

## 符合以下规范

- Copyable

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollPosition
crawled: 2025-12-02T17:40:18Z
---

# ScrollPosition

**Structure**

A type that defines the semantic position of where a scroll view is scrolled within its content.

## Declaration

```swift
struct ScrollPosition
```

## Overview

Use this type along with the `View/scrollPosition(_:)` modifier to control where a scroll view is positioned. You can use this type to scroll in a variety of ways:

- scroll to a view with a provided identity
- scroll to a concrete offset
- scroll to an edge

You can create a scroll position with a specified view identity type

```swift
@State private var position = ScrollPosition(idType: MyItem.ID.self)
```

SwiftUI will use that along with the views in the scroll view’s scroll target layout to programmatically scroll to those views and to update the [viewID](ScrollPosition/viewID.zh-Hans.md) property as the user scrolls. Use the `View/scrollTargetLayout()` modifier to configure which layout contains your scroll targets.

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
.scrollPosition($scrolledID)
```

You can then query the currently scrolled id by using the [viewID(type:)](ScrollPosition/viewID_type.zh-Hans.md).

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
.scrollPosition($scrolledID, anchor: .bottom)
```

For example, providing a value of [bottom](UnitPoint/bottom.zh-Hans.md) will prefer to have the bottom-most view chosen and prefer to scroll to views aligned to the bottom.

If no anchor has been provided, SwiftUI will scroll the minimal amount when using the scroll position to programmatically scroll to a view.

## Initializers

- **init(id:anchor:)**: Creates a new scroll position to a view with a provided identity value.
- **init(idType:)**: Creates a new automatic scroll position.
- **init(idType:edge:)**: Creates a new scroll position to be scrolled to the provided edge.
- **init(idType:point:)**: Creates a new scroll position to be scrolled to the provided point.
- **init(idType:x:)**: Creates a new scroll position to be scrolled to the provided y value.
- **init(idType:x:y:)**: Creates a new scroll position to be scrolled to the provided x value.
- **init(idType:y:)**: Creates a new scroll position to be scrolled to the provided y value.

## Instance Properties

- **edge**: The positioned edge of the scroll view if configured to be in that position.
- **isPositionedByUser**: Whether the scroll view has been positioned by the user.
- **point**: The positioned point of the scroll view if configured to be in that position.
- **viewID**: The type-erased id of the view positioned in the scroll view if configured to be in that position or the user has scrolled past a view with an id of matching type.
- **x**: The positioned x value of the scroll view if configured to be in that position.
- **y**: The positioned y value of the scroll view if configured to be in that position.

## Instance Methods

- **scrollTo(edge:)**: Scrolls the position of the scroll view to the edge you provide.
- **scrollTo(id:anchor:)**: Scrolls the position of the scroll view to a view with a identity value and anchor you provide.
- **scrollTo(point:)**: Scrolls the position of the scroll view to the point you provide.
- **scrollTo(x:)**: Scrolls the position of the scroll view to the x value you provide.
- **scrollTo(x:y:)**: Scrolls the position of the scroll view to the x and y value you provide.
- **scrollTo(y:)**: Scrolls the position of the scroll view to the y value you provide.
- **viewID(type:)**: The id of the view positioned in the scroll view if configured to be in that position or the user has scrolled past a view with an id of matching type.

## Managing scroll position

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **ScrollAnchorRole**: A type defining the role of a scroll anchor.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype

