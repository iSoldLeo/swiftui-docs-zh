---
来源： https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect
抓取时间：2025-12-02T17:42:00Z
---

# 自定义悬停效果

**Protocol**

一种表示当指针悬停在视图上或有人注视视图时，视图应如何变化的类型。

### 声明

```swift
protocol CustomHoverEffect
```

## 概览

自定义悬停效果在效果处于非活动状态时应用其非活动值，而在效果处于活动状态时应用其活动值。例如，以下特效会使视图在不活动时部分透明，而在活动时则完全不透明：

```swift
struct FadeInHoverEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, proxy in
            effect.animation(.easeOut) {
                $0.opacity(isActive ? 1 : 0.5)
            }
        }
    }
}
```

可以使用`hoverEffect(_:)` 修改器将此效果应用于视图：

```swift
Color.red
    .hoverEffect(FadeInHoverEffect())
```

悬停效果不会影响视图的布局，并且可以在进程外应用于视图。因此，在您的应用程序中可能看不到效果的当前阶段。

## 获取内置悬停效果

- **automatic**：基于周围环境的默认悬停效果。
- **empty**：悬停时不会发生变化的效果。
- **highlight**：一种悬停效果，可使用光源突出显示视图以指示位置。
- **lift**：一种悬停效果，可将指针滑动到视图下方，并随着视图的缩放和阴影的增加而消失。

## 创建自定义悬停效果

- **hoverEffect(_:in:isEnabled:)**：与给定的 `effect`同时应用此特效。
- **hoverEffect(in:isEnabled:body:)**：根据当前阶段应用悬停效果。
- **hoverEffectGroup(_:)**：将此特效作为特效组的一部分激活。
- **hoverEffectGroup(id:in:behavior:)**：作为效果组的一部分激活此效果。
- **hoverEffectDisabled(_:)**：禁用此悬停效果。

## 支持类型

- **AutomaticHoverEffect**：基于周围环境的默认悬停效果。
- **EmptyHoverEffect**：用于构建附加效果的基本悬停效果。
- **HighlightHoverEffect**：一种悬停效果，可使用光源指示位置来突出显示视图。
- **LiftHoverEffect**：一种悬停效果，可将指针滑动到视图下方，并随着视图的缩放和阴影的增加而消失。

### 相关类型

- **Body**：代表此特效主体的特效类型。创建自定义特效时，Swift 会根据您对所需 [body(content:)](CustomHoverEffect/body_content.zh-Hans.md) 方法的实现推断出该类型。

### 实例方法

- **body(content:)**：定义此特效产生的效果。
- **hoverEffectPhaseOverride(_:)**：将给定的`HoverEffectPhaseOverride`应用到此特效，并返回一个新特效。

### 类型别名

- **CustomHoverEffect.Content**：传递给 `body(content:)` 的内容效果类型。

### 类型方法

- **hoverEffect(in:isEnabled:body:)**：创建悬停效果，使用给定的闭包将效果应用到视图。
- **hoverEffectGroup(_:)**：创建激活指定特效组的特效。
- **hoverEffectGroup(id:in:behavior:)**：**hoverEffectGroup(id:in:behavior:)**： 创建一个能激活指定效果组的效果。
- **ornament(attachmentAnchor:contentAlignment:ornament:)**：悬停时显示装饰物。
- **ornament(attachmentAnchor:contentAlignment:ornament:effect:)**：悬停时显示装饰品。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。
- **HoverEffect**：指针悬停在视图上时应用的效果。
- **hoverEffect(_:in:isEnabled:)**：将悬停效果应用到该视图，可选择将其添加到 [HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。
- **hoverEffect(in:isEnabled:body:)**：为给定闭合描述的视图应用悬停效果。
- **ContentHoverEffect**：`CustomHoverEffect`：使用闭包将悬停效果应用到视图。
- **HoverEffectGroup**：描述一组一起激活的特效。
- **hoverEffectGroup()**：将隐式[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效，这样，只要悬停此视图或任何后代视图，添加到子视图上的所有特效都会作为一组激活。
- **hoverEffectGroup(_:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效中，并在此视图或任何后代视图悬停时激活该组特效。
- **hoverEffectGroup(id:in:behavior:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效，并在此视图或任何后代视图悬停时激活该组。
- **GroupHoverEffect**：用于激活指定效果组的`CustomHoverEffect`。
- **HoverEffectContent**：描述特定悬停效果阶段的视图效果的类型。
- **EmptyHoverEffectContent**：用于构建其他效果的空基础效果。
- **handPointerBehavior(_:)**：设置用户与视图交互时手部指针的行为。
- **HandPointerBehavior**：用户与视图交互时可应用于手形指针的行为。

## 符合类型

- 自动悬停效果
- 内容悬停效果
- 空悬停效果
- 分组悬停效果
- 高亮显示效果
- 悬停效果
- 提升悬停效果
- 修改内容
- 饰品悬停内容效果
- 饰品悬停效果


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect
crawled: 2025-12-02T17:42:00Z
---

# CustomHoverEffect

**Protocol**

A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.

## Declaration

```swift
protocol CustomHoverEffect
```

## Overview

Custom hover effects apply their inactive values when the effect is inactive, and their active values when the effect is active. For example, the following effect causes a view to be partially transparent when inactive, but animate to fully opaque when active:

```swift
struct FadeInHoverEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, proxy in
            effect.animation(.easeOut) {
                $0.opacity(isActive ? 1 : 0.5)
            }
        }
    }
}
```

This effect can be applied to a view using the `hoverEffect(_:)` modifier:

```swift
Color.red
    .hoverEffect(FadeInHoverEffect())
```

Hover effects do not affect a view’s layout, and may be applied to a view out-of-process. Therefore an effect’s current phase may not be visible within your app.

## Getting built-in hover effects

- **automatic**: The default hover effect based on the surrounding context.
- **empty**: An effect that applies no changes when hovered.
- **highlight**: A hover effect that highlights views using a light source to indicate position.
- **lift**: A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

## Creating custom hover effects

- **hoverEffect(_:in:isEnabled:)**: Applies this effect in parallel with the given `effect`.
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect based on the current phase.
- **hoverEffectGroup(_:)**: Activates this effect as part of an effect group.
- **hoverEffectGroup(id:in:behavior:)**: Activates this effect as part of an effect group.
- **hoverEffectDisabled(_:)**: Disables this hover effect.

## Supporting types

- **AutomaticHoverEffect**: The default hover effect based on the surrounding context.
- **EmptyHoverEffect**: A base hover effect used to build additional effects.
- **HighlightHoverEffect**: A hover effect that highlights views using a light source to indicate position.
- **LiftHoverEffect**: A hover effect that slides the pointer under the view and disappears as the view scales up and gains a shadow.

## Associated Types

- **Body**: The type of effect representing the body of this effect. When you create a custom effect, Swift infers this type from your implementation of the required [body(content:)](CustomHoverEffect/body_content.zh-Hans.md) method.

## Instance Methods

- **body(content:)**: Defines the effect produced by this effect.
- **hoverEffectPhaseOverride(_:)**: Returns a new effect with the given `HoverEffectPhaseOverride` applied to this effect.

## Type Aliases

- **CustomHoverEffect.Content**: The content effect type passed to `body(content:)`.

## Type Methods

- **hoverEffect(in:isEnabled:body:)**: Creates a hover effect that applies effects to a view using the given closure.
- **hoverEffectGroup(_:)**: Creates an effect that activates a named group of effects.
- **hoverEffectGroup(id:in:behavior:)**: Creates an effect that activates a named group of effects.
- **ornament(attachmentAnchor:contentAlignment:ornament:)**: Presents an ornament on hover.
- **ornament(attachmentAnchor:contentAlignment:ornament:effect:)**: Presents an ornament on hover.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **HoverEffectGroup**: Describes a grouping of effects that activate together.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

## Conforming Types

- AutomaticHoverEffect
- ContentHoverEffect
- EmptyHoverEffect
- GroupHoverEffect
- HighlightHoverEffect
- HoverEffect
- LiftHoverEffect
- ModifiedContent
- OrnamentHoverContentEffect
- OrnamentHoverEffect

