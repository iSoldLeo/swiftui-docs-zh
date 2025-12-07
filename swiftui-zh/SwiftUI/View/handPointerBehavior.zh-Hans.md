--- 来源：https://developer.apple.com/documentation/SwiftUI/View/handPointerBehavior(_:)

抓取时间：2025-12-02T17:23:55Z

---

# handPointerBehavior(_:)

**实例方法**

设置用户与视图交互时手形指针的行为。

## 声明

```swift
nonisolated func handPointerBehavior(_ behavior: HandPointerBehavior?) -> some View

```

## 参数

- **behavior**：要应用于手形指针的行为。如果为 `nil`，则手形指针的行为将从视图的祖先继承。

## 返回值

一个应用了给定行为的手形指针视图。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

- **hoverEffect(in:isEnabled:body:)**：为该视图应用由给定闭包描述的悬停效果。

- **CustomHoverEffect**：一种类型，表示指针悬停在视图上或用户查看视图时视图应如何变化。

- **ContentHoverEffect**：一个 `CustomHoverEffect`，使用闭包在悬停时为视图应用效果。

- **HoverEffectGroup**：描述一组同时激活的效果。

- **hoverEffectGroup()**：为所有子视图上定义的效果添加一个隐式的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，使得当鼠标悬停在该视图或任何子视图上时，添加到子视图的所有效果都会作为一个整体激活。

- **hoverEffectGroup(_:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停在该视图或任何子视图上时激活该效果组。

- **hoverEffectGroup(id:in:behavior:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停在该视图或任何子视图上时激活该效果组。

- **GroupHoverEffect**：一个用于激活指定效果组的 `CustomHoverEffect`。

- **HoverEffectContent**：一种类型，用于描述视图在特定悬停效果阶段的效果。

- **EmptyHoverEffectContent**：一个空的基础效果，可用于构建其他效果。

- **HandPointerBehavior**：一种行为，可在用户与视图交互时应用于手形指针。


---
source: https://developer.apple.com/documentation/SwiftUI/View/handPointerBehavior(_:)
crawled: 2025-12-02T17:23:55Z
---

# handPointerBehavior(_:)

**Instance Method**

Sets the behavior of the hand pointer while the user is interacting with the view.

## Declaration

```swift
nonisolated func handPointerBehavior(_ behavior: HandPointerBehavior?) -> some View

```

## Parameters

- **behavior**: The behavior to apply to the hand pointer. If `nil`, the hand pointer behavior will be inherited from the view’s ancestors.

## Return Value

A view that applies the given behavior to the hand pointer.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **CustomHoverEffect**: A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **HoverEffectGroup**: Describes a grouping of effects that activate together.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

