--- 来源：https://developer.apple.com/documentation/SwiftUI/OrnamentHoverEffect
抓取时间：2025-12-02T17:41:54Z

---

# OrnamentHoverEffect

**Structure**

鼠标悬停时显示装饰效果。

## 声明

```swift
struct OrnamentHoverEffect<OrnamentView> where OrnamentView : View
```

## 概述

请勿直接使用此组件。请使用 `CustomHoverEffect.ornament` 创建装饰效果。

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移至视图框架上方或下方时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制该视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰。

## 符合以下规范

- CustomHoverEffect


---
source: https://developer.apple.com/documentation/SwiftUI/OrnamentHoverEffect
crawled: 2025-12-02T17:41:54Z
---

# OrnamentHoverEffect

**Structure**

Presents an ornament on hover.

## Declaration

```swift
struct OrnamentHoverEffect<OrnamentView> where OrnamentView : View
```

## Overview

You don’t use this directly. Use `CustomHoverEffect.ornament` to create ornament effects instead.

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.

## Conforms To

- CustomHoverEffect

