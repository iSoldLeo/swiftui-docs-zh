--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(_:in:isEnabled:)

抓取时间：2025-12-02T17:41:59Z

---

# hoverEffect(_:in:isEnabled:)

**实例方法**

为该视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

## 声明

```swift
nonisolated func hoverEffect(_ effect: some CustomHoverEffect, in group: HoverEffectGroup?, isEnabled: Bool = true) -> some View

```

## 参数

- **effect**：要应用于此视图的效果。

- **group**：效果所属的可选 `HoverEffectGroup`。

- **isEnabled**：此效果是否已启用。

## 返回值

当鼠标悬停在视图上或激活 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) 时，将悬停效果应用于 `self` 的新视图。

## 悬停事件时更改视图外观

- **hoverEffect(_:)**：将悬停效果应用于此视图。

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(in:isEnabled:body:)**：将给定闭包描述的悬停效果应用于此视图。

- **CustomHoverEffect**：表示当指针悬停在视图上或有人查看视图时，视图应如何变化的类型。

- **ContentHoverEffect**：使用闭包在悬停时将效果应用于视图的 `CustomHoverEffect`。 - **HoverEffectGroup**：描述一组同时激活的效果。

- **hoverEffectGroup()**：为所有子视图上定义的效果添加一个隐式的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，使得当鼠标悬停在该视图或任何子视图上时，添加到子视图的所有效果都会作为一个整体激活。

- **hoverEffectGroup(_:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停在该视图或任何子视图上时激活该效果组。

- **hoverEffectGroup(id:in:behavior:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停在该视图或任何子视图上时激活该效果组。

- **GroupHoverEffect**：一个用于激活指定效果组的 `CustomHoverEffect`。

- **HoverEffectContent**：一种类型，用于描述视图在特定悬停效果阶段的效果。

- **EmptyHoverEffectContent**：一个空的基础效果，可用于构建其他效果。

- **handPointerBehavior(_:)**：设置用户与视图交互时手形指针的行为。

- **HandPointerBehavior**：一种可在用户与视图交互时应用于手形指针的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(_:in:isEnabled:)
crawled: 2025-12-02T17:41:59Z
---

# hoverEffect(_:in:isEnabled:)

**Instance Method**

Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md).

## Declaration

```swift
nonisolated func hoverEffect(_ effect: some CustomHoverEffect, in group: HoverEffectGroup?, isEnabled: Bool = true) -> some View

```

## Parameters

- **effect**: The effect to apply to this view.
- **group**: An optional `HoverEffectGroup` the effect should belong to.
- **isEnabled**: Whether this effect is enabled or not.

## Return Value

A new view that applies the hover effect to `self` whenever the view is hovered, or the [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) is activated.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
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
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

