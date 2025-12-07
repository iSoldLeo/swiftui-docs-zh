--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(_:)

抓取时间：2025-12-02T17:41:57Z

---

# hoverEffect(_:)

**实例方法**

为当前视图应用悬停效果。

## 声明

```swift
nonisolated func hoverEffect(_ effect: HoverEffect = .automatic) -> some View

```

## 参数

- **effect**：要应用到当前视图的效果。

## 返回值

一个应用了悬停效果的新视图，该效果应用于 `self`。

## 说明

默认情况下，使用 [automatic](../HoverEffect/automatic.zh-Hans.md)。您可以使用 [defaultHoverEffect(_:)](defaultHoverEffect.zh-Hans.md) 修饰符来控制自动效果的行为。

## 悬停事件时更改视图外观

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(_:in:isEnabled:)**：将悬停效果应用于此视图，并可选择将其添加到 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

- **hoverEffect(in:isEnabled:body:)**：将给定闭包描述的悬停效果应用于此视图。

- **CustomHoverEffect**：一种类型，表示指针悬停在视图上或用户查看视图时视图应如何变化。

- **ContentHoverEffect**：一个 `CustomHoverEffect`，使用闭包在悬停时将效果应用于视图。

- **HoverEffectGroup**：描述一组同时激活的效果。

- **hoverEffectGroup()**：为所有子视图上定义的效果添加一个隐式的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，使得当鼠标悬停在该视图或任何子视图上时，添加到子视图的所有效果都会作为一个整体激活。

- **hoverEffectGroup(_:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停在该视图或任何子视图上时激活该效果组。

- **hoverEffectGroup(id:in:behavior:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停在该视图或任何子视图上时激活该效果组。

- **GroupHoverEffect**：一个 `CustomHoverEffect`，用于激活一个指定的效果组。

- **HoverEffectContent**：描述视图在特定悬停效果阶段所呈现效果的类型。

- **EmptyHoverEffectContent**：用于构建其他效果的空基础效果。

- **handPointerBehavior(_:)**：设置用户与视图交互时手形指针的行为。

- **HandPointerBehavior**：用户与视图交互时可应用于手形指针的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(_:)
crawled: 2025-12-02T17:41:57Z
---

# hoverEffect(_:)

**Instance Method**

Applies a hover effect to this view.

## Declaration

```swift
nonisolated func hoverEffect(_ effect: HoverEffect = .automatic) -> some View

```

## Parameters

- **effect**: The effect to apply to this view.

## Return Value

A new view that applies a hover effect to `self`.

## Discussion

By default, [automatic](../HoverEffect/automatic.zh-Hans.md) is used. You can control the behavior of the automatic effect with the [defaultHoverEffect(_:)](defaultHoverEffect.zh-Hans.md) modifier.

## Changing view appearance for hover events

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
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

