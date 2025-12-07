--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride
抓取时间：2025-12-02T17:41:52Z

---

# HoverEffectPhaseOverride

**Structure**

用于覆盖悬停效果当前阶段的选项。

## 声明

```swift
struct HoverEffectPhaseOverride
```

## 概述

默认情况下，悬停效果会在悬停事件发生时在激活阶段和非激活阶段之间切换。使用 `HoverEffectPhaseOverride` 可以根据其他条件使悬停效果在阶段之间切换。

## 类型属性

- **active**：立即切换到激活阶段。

- **inactive**：立即切换到非激活阶段。

## 类型方法

- **activeTemporarily(trigger:)**：暂时切换到活动阶段，直到所有动画播放完毕，切换完成。

- **inactiveTemporarily(trigger:)**：暂时切换到非活动阶段，直到所有动画播放完毕，切换完成。

- **toggled(trigger:)**：立即切换到与效果当前阶段相反的阶段。

- **toggledTemporarily(trigger:)**：在应用覆盖时，暂时切换到与效果当前阶段相反的阶段。

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移到视图框架上方或下方时执行该操作。

- **onContinuousHover(coordinateSpace:perform:)**：添加指针进入、移动到视图边界内以及离开视图边界时要执行的操作。

- **hoverEffect(_:isEnabled:)**：为此视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制此视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰。

- **OrnamentHoverEffect**：鼠标悬停时显示装饰图案。

## 符合以下标准

- Equatable


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride
crawled: 2025-12-02T17:41:52Z
---

# HoverEffectPhaseOverride

**Structure**

Options for overriding a hover effect’s current phase.

## Declaration

```swift
struct HoverEffectPhaseOverride
```

## Overview

By default hover effects transition between the active and inactive phases in response to hover events. Use `HoverEffectPhaseOverride` to cause a hover effect to transition between phases based on other criteria.

## Type Properties

- **active**: Immediately transition to the active phase.
- **inactive**: Immediately transition to the inactive phase.

## Type Methods

- **activeTemporarily(trigger:)**: Temporaily transitions to the active phase until all animations finish, and the transition is complete.
- **inactiveTemporarily(trigger:)**: Temporaily transitions to the inactve phase until all animations finish, and the transition is complete.
- **toggled(trigger:)**: Immediately transition to the opposite of an effect’s current phase.
- **toggledTemporarily(trigger:)**: Temporaily transitions to the opposite of the effect’s current phase at the moment the override is applied.

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

## Conforms To

- Equatable

