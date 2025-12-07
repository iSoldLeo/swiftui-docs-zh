--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(in:isEnabled:body:)

抓取时间：2025-12-02T17:42:00Z

---

# hoverEffect(in:isEnabled:body:)

**实例方法**

将悬停效果应用于由给定闭包描述的视图。

## 声明

```swift
nonisolated func hoverEffect(in group: HoverEffectGroup? = nil, isEnabled: Bool = true, body: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> some HoverEffectContent) -> some View

```

## 参数

- **group**：可选的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，用于指定要添加此效果的对象。

- **isEnabled**：效果是否启用。如果 `false`，则效果处于非激活状态，悬停时不会应用激活状态。

- **body**：为效果的每个阶段构造一个 `HoverEffectContent` 的闭包。

## 返回值

一种新的效果，当鼠标悬停在视图上时，视图的外观会发生改变。

## 说明

您可以使用此修改器来描述鼠标悬停在视图上时应该如何改变视图。给定的代码块包含一个空的效果，您可以使用它来组合效果，以及一个布尔值，用于描述请求的阶段。此外，还提供了一个 [GeometryProxy](../GeometryProxy.zh-Hans.md)，允许效果根据视图的几何形状而改变。

在以下示例中，`Text` 在非活动状态下缩放比例为 1.0，鼠标悬停时缩放比例为 1.1：

```swift
Text("Hello, World!")
    .hoverEffect { effect, isActive, proxy in
        effect.scaleEffect(!isActive ? 1.0 : 1.1)
    }
```

使用 [animation(_:body:)](../HoverEffectContent/animation___body.zh-Hans.md) 修改器来指定视觉变化的动画方式。

## 悬停事件时更改视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

- **CustomHoverEffect**：一种类型，表示指针悬停在视图上或用户查看视图时视图应如何变化。

- **ContentHoverEffect**：一个 `CustomHoverEffect`，使用闭包在悬停时为视图应用效果。

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
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(in:isEnabled:body:)
crawled: 2025-12-02T17:42:00Z
---

# hoverEffect(in:isEnabled:body:)

**Instance Method**

Applies a hover effect to this view described by the given closure.

## Declaration

```swift
nonisolated func hoverEffect(in group: HoverEffectGroup? = nil, isEnabled: Bool = true, body: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> some HoverEffectContent) -> some View

```

## Parameters

- **group**: An optional [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to add this effect to.
- **isEnabled**: Whether the effect is enabled or not. If `false`, the effect’s inactive state will be applied, and it will not apply the active state when hovered.
- **body**: The closure that constructs a `HoverEffectContent` for each of the effect’s phases.

## Return Value

A new effect that changes a view’s appearance when hovered.

## Discussion

You use this modifier to describe how a view should change when hovered. The given block is provided an empty effect that you use to compose effects, as well as a boolean describing which phase is being requested. A [GeometryProxy](../GeometryProxy.zh-Hans.md) is also provided, allowing effects to change based on the view’s geometry.

In the following example, the `Text` will have a scale of 1.0 when inactive, and then scale to 1.1 when hovered:

```swift
Text("Hello, World!")
    .hoverEffect { effect, isActive, proxy in
        effect.scaleEffect(!isActive ? 1.0 : 1.1)
    }
```

Use the [animation(_:body:)](../HoverEffectContent/animation___body.zh-Hans.md) modifier to specify how visual changes should be animated.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md).
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

