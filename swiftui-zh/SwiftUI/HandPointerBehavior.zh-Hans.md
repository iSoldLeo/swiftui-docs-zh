---
来源： https://developer.apple.com/documentation/SwiftUI/HandPointerBehavior
抓取时间： 2025-12-02T17:42:08Z
---

# HandPointerBehavior

**Structure**

当用户与视图交互时，可应用于手指针的行为。

## 声明

```swift
struct HandPointerBehavior
```

## 类型属性

- **drawing**：启用用于绘图的精炼手形指针。
- **inactive**：停用视图内的手形指针。使用此功能可确保视图不会应用任何手形指针行为，而不管应用于层次结构中的祖先的行为如何。

## 为悬停事件更改视图外观

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
- **GroupHoverEffect**：用于激活指定效果组的`CustomHoverEffect`。
- **HoverEffectContent**：描述特定悬停效果阶段的视图效果的类型。
- **EmptyHoverEffectContent**：用于构建其他效果的空基础效果。
- **handPointerBehavior(_:)**：设置用户与视图交互时手部指针的行为。

## 符合

- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/HandPointerBehavior
crawled: 2025-12-02T17:42:08Z
---

# HandPointerBehavior

**Structure**

A behavior that can be applied to the hand pointer while the user is interacting with a view.

## Declaration

```swift
struct HandPointerBehavior
```

## Type Properties

- **drawing**: Enables the hand pointer refined for drawing.
- **inactive**: Deactivates the hand pointer inside the view. Use this to ensure the view will not apply any hand pointer behavior regardless of behaviors applied to ancestors in the hierarchy.

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
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.

## Conforms To

- Equatable

