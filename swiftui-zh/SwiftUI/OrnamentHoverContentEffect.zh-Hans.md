---
来源： https://developer.apple.com/documentation/SwiftUI/OrnamentHoverContentEffect
抓取时间： 2025-12-02T17:41:53Z
---

# OrnamentHoverContentEffect

**Structure**

使用自定义效果在悬停时显示装饰物。

## 声明

```swift
struct OrnamentHoverContentEffect<OrnamentView, OrnamentContentEffect> where OrnamentView : View, OrnamentContentEffect : HoverEffectContent
```

## 概览

不能直接使用。请使用 `CustomHoverEffect.ornament` 创建装饰效果。

## 响应悬停事件

- **onHover(perform:)**：当用户将指针移至视图框架上方或远离视图框架时，添加一个要执行的操作。
- **onContinuousHover(coordinateSpace:perform:)**：添加当指针进入、在视图范围内移动或退出视图范围时要执行的操作。
- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。
- **hoverEffectDisabled(_:)**：添加控制此视图能否显示悬停效果的条件。
- **defaultHoverEffect(_:)**：为该视图中的视图设置默认的悬停效果。
- **isHoverEffectEnabled**：布尔值，表示与此环境关联的视图是否允许显示悬停效果。
- **HoverPhase**：指针当前的悬停状态和值。
- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。
- **OrnamentHoverEffect**：在悬停时显示装饰物。

## 符合

- 自定义悬停效果


---
source: https://developer.apple.com/documentation/SwiftUI/OrnamentHoverContentEffect
crawled: 2025-12-02T17:41:53Z
---

# OrnamentHoverContentEffect

**Structure**

Presents an ornament on hover using a custom effect.

## Declaration

```swift
struct OrnamentHoverContentEffect<OrnamentView, OrnamentContentEffect> where OrnamentView : View, OrnamentContentEffect : HoverEffectContent
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
- **OrnamentHoverEffect**: Presents an ornament on hover.

## Conforms To

- CustomHoverEffect

