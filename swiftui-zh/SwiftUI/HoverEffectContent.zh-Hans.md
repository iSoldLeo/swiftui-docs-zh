---
来源： https://developer.apple.com/documentation/SwiftUI/HoverEffectContent
抓取时间： 2025-12-02T17:42:06Z
---

# HoverEffectContent

**Protocol**

一种类型，用于描述特定悬停效果阶段的视图效果。

## 声明

```swift
protocol HoverEffectContent
```

## 概览

```swift
Color.red
    .hoverEffect { effect, isActive, proxy in
        effect.opacity(isActive ? 1 : 0.5)
    }
```

你自己并不遵守这一协议。相反，特效是通过调用其他特效的修饰符函数来描述的，例如上面例子中使用的`opacity(_:)`修饰符。

### 实例方法

- **animation(_:body:)**：将给定的[Animation](Animation.zh-Hans.md) 应用于`body` 闭合中的所有效果。
- **clipShape(_:style:)**：为视图设置剪贴形状。
- **offset(_:)**：按偏移参数中指定的水平和垂直量偏移视图。
- **offset(x:y:)**：按指定的水平和垂直距离偏移视图。
- **opacity(_:)**：设置视图的透明度。
- **rotationEffect(_:anchor:)**：围绕指定点旋转二维内容。
- **scaleEffect(_:anchor:)**：相对于一个锚点，在水平和垂直方向上以给定的量缩放视图的渲染输出。
- **scaleEffect(x:y:anchor:)**：相对于一个锚点，按给定的水平和垂直方向量缩放视图的渲染输出。
- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为该视图应用悬停效果。
- **HoverEffect**：当指针悬停在视图上时应用的效果。
- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，可选择将其添加到[HoverEffectGroup](HoverEffectGroup.zh-Hans.md)。
- **hoverEffect(in:isEnabled:body:)**：为给定闭合描述的视图应用悬停效果。
- **CustomHoverEffect**：表示当指针悬停在视图上或有人注视视图时视图应如何变化的类型。
- **ContentHoverEffect**：`CustomHoverEffect`：使用闭包对悬停时的视图应用特效。
- **HoverEffectGroup**：描述一组一起激活的特效。
- **hoverEffectGroup()**：为后代视图中定义的所有特效添加隐式[HoverEffectGroup](HoverEffectGroup.zh-Hans.md)，这样，只要悬停此视图或任何后代视图，添加到子视图中的所有特效都会作为一组激活。
- **hoverEffectGroup(_:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效中，并在此视图或任何后代视图悬停时激活该组特效。
- **hoverEffectGroup(id:in:behavior:)**：将[HoverEffectGroup](HoverEffectGroup.zh-Hans.md) 添加到定义在后代视图上的所有特效，并在此视图或任何后代视图悬停时激活该组。
- **GroupHoverEffect**：用于激活指定效果组的`CustomHoverEffect`。
- **EmptyHoverEffectContent**：空的基础效果，用于构建其他效果。
- **handPointerBehavior(_:)**：设置用户与视图交互时手部指针的行为。
- **HandPointerBehavior**：用户与视图交互时可应用于手形指针的行为。

## 符合类型

- EmptyHoverEffectContent（空悬停效果内容
- 修改内容


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent
crawled: 2025-12-02T17:42:06Z
---

# HoverEffectContent

**Protocol**

A type that describes the effects of a view for a particular hover effect phase.

## Declaration

```swift
protocol HoverEffectContent
```

## Overview

```swift
Color.red
    .hoverEffect { effect, isActive, proxy in
        effect.opacity(isActive ? 1 : 0.5)
    }
```

You don’t conform to this protocol yourself. Instead, effects are described by calling modifier functions on other effects, like the `opacity(_:)` modifier used in the example above.

## Instance Methods

- **animation(_:body:)**: Applies the given [Animation](Animation.zh-Hans.md) to all effects within the `body` closure.
- **clipShape(_:style:)**: Sets a clipping shape for the view.
- **offset(_:)**: Offsets the view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offsets the view by the specified horizontal and vertical distances.
- **opacity(_:)**: Sets the transparency of the view.
- **rotationEffect(_:anchor:)**: Rotates content in two dimensions around the specified point.
- **scaleEffect(_:anchor:)**: Scales the view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales the view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **transformEffect(_:)**: Applies an affine transformation to the view’s rendered output.

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
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

## Conforming Types

- EmptyHoverEffectContent
- ModifiedContent

