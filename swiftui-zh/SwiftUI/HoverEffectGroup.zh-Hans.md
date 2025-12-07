---
来源： https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup
抓取时间： 2025-12-02T17:42:02Z
---

# HoverEffectGroup

**Structure**

描述一组一起激活的效果。

## 声明

```swift
struct HoverEffectGroup
```

## 概览

使用 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 将特效同步应用于多个视图。

## 结构

- **HoverEffectGroup.Behavior**：描述一组特效的行为。

## 初始化器

- **init(_:behavior:)**：从`Namespace.ID` 创建一个新的[HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。
- **init(id:in:behavior:)**：创建新的[HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。

### 实例方法

- **behavior(_:)**：用给定的 `behavior` 返回`self` 的新版本。

### 类型属性

- **systemOverlays**：`HoverEffectGroup`，在系统覆盖可见时处于活动状态。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。
- **HoverEffect**：指针悬停在视图上时应用的效果。
- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，可选择将其添加到[HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。
- **hoverEffect(in:isEnabled:body:)**：为给定闭合描述的视图应用悬停效果。
- **CustomHoverEffect**：表示当指针悬停在视图上或有人注视视图时视图应如何变化的类型。
- **ContentHoverEffect**：`CustomHoverEffect`：使用闭包对悬停时的视图应用特效。
- **hoverEffectGroup()**：将隐式[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效中，这样，每当该视图或任何后代视图悬停时，添加到子视图上的所有特效都会作为一组激活。
- **hoverEffectGroup(_:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效中，并在此视图或任何后代视图悬停时激活该组特效。
- **hoverEffectGroup(id:in:behavior:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效，并在此视图或任何后代视图悬停时激活该组。
- **GroupHoverEffect**：用于激活指定效果组的`CustomHoverEffect`。
- **HoverEffectContent**：描述特定悬停效果阶段的视图效果的类型。
- **EmptyHoverEffectContent**：用于构建其他效果的空基础效果。
- **handPointerBehavior(_:)**：设置用户与视图交互时手部指针的行为。
- **HandPointerBehavior**：用户与视图交互时可应用于手形指针的行为。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup
crawled: 2025-12-02T17:42:02Z
---

# HoverEffectGroup

**Structure**

Describes a grouping of effects that activate together.

## Declaration

```swift
struct HoverEffectGroup
```

## Overview

Use [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to apply effects to multiple views in concert.

## Structures

- **HoverEffectGroup.Behavior**: Describes the behavior of an effect in a group.

## Initializers

- **init(_:behavior:)**: Creates a new [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) from a `Namespace.ID`.
- **init(id:in:behavior:)**: Creates a new [HoverEffectGroup](HoverEffectGroup.zh-Hans.md).

## Instance Methods

- **behavior(_:)**: Returns a new version of `self` with the given `behavior`.

## Type Properties

- **systemOverlays**: A `HoverEffectGroup` that becomes active when system overlays are visible.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **CustomHoverEffect**: A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

