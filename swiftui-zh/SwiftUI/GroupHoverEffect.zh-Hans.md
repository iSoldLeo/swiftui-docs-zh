---
来源： https://developer.apple.com/documentation/SwiftUI/GroupHoverEffect
抓取时间： 2025-12-02T17:42:05Z
---

# GroupHoverEffect

**Structure**

用于激活指定效果组的`CustomHoverEffect`。

## 声明

```swift
struct GroupHoverEffect
```

## 概览

使用 [hoverEffectGroup(_:)-swift.type.method](CustomHoverEffect/hoverEffectGroup___-swift_type_method.zh-Hans.md) 或 [hoverEffectGroup(id:in:behavior:)-swift.type.method](CustomHoverEffect/hoverEffectGroup_id_in_behavior_-swift_type_method.zh-Hans.md) 方法构建[GroupHoverEffect](GroupHoverEffect.zh-Hans.md)。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。
- **HoverEffect**：指针悬停在视图上时应用的效果。
- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，可选择将其添加到[HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。
- **hoverEffect(in:isEnabled:body:)**：为给定闭合描述的视图应用悬停效果。
- **CustomHoverEffect**：表示当指针悬停在视图上或有人注视视图时视图应如何变化的类型。
- **ContentHoverEffect**：`CustomHoverEffect`：使用闭包对悬停时的视图应用特效。
- **HoverEffectGroup**：描述一组一起激活的特效。
- **hoverEffectGroup()**：将隐式[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效，这样，只要悬停此视图或任何后代视图，添加到子视图上的所有特效都会作为一组激活。
- **hoverEffectGroup(_:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效中，并在此视图或任何后代视图悬停时激活该组特效。
- **hoverEffectGroup(id:in:behavior:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效，并在此视图或任何后代视图悬停时激活该组。
- **HoverEffectContent**：描述视图在特定悬停效果阶段的效果的类型。
- **EmptyHoverEffectContent**：用于构建其他效果的空基础效果。
- **handPointerBehavior(_:)**：设置用户与视图交互时手部指针的行为。
- **HandPointerBehavior**：用户与视图交互时可应用于手形指针的行为。

## 符合

- 可复制
- 自定义悬停效果


---
source: https://developer.apple.com/documentation/SwiftUI/GroupHoverEffect
crawled: 2025-12-02T17:42:05Z
---

# GroupHoverEffect

**Structure**

A `CustomHoverEffect` that activates a named group of effects.

## Declaration

```swift
struct GroupHoverEffect
```

## Overview

Use the [hoverEffectGroup(_:)-swift.type.method](CustomHoverEffect/hoverEffectGroup___-swift_type_method.zh-Hans.md) or [hoverEffectGroup(id:in:behavior:)-swift.type.method](CustomHoverEffect/hoverEffectGroup_id_in_behavior_-swift_type_method.zh-Hans.md) methods to construct a [GroupHoverEffect](GroupHoverEffect.zh-Hans.md).

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **CustomHoverEffect**: A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **HoverEffectGroup**: Describes a grouping of effects that activate together.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

## Conforms To

- Copyable
- CustomHoverEffect

