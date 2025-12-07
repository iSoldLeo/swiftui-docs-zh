--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverPhase
抓取时间：2025-12-02T17:41:52Z

---

# HoverPhase

**Enumeration**

指针的当前悬停状态和值。

## 声明

```swift
@frozen enum HoverPhase
```

## 概述

使用 [onContinuousHover(coordinateSpace:perform:)](View/onContinuousHover_coordinateSpace_perform.zh-Hans.md) 修饰符时，可以使用 `action` 闭包来处理悬停状态。SwiftUI 会调用该闭包并传入一个阶段值来指示当前的悬停状态。以下示例根据提供给闭包的阶段更新 `hoverLocation` 和 `isHovering`：

```swift
@State private var hoverLocation: CGPoint = .zero
@State private var isHovering = false

var body: some View {
    VStack {
        Color.red
            .frame(width: 400, height: 400)
            .onContinuousHover { phase in
                switch phase {
                case .active(let location):
                    hoverLocation = location
                    isHovering = true
                case .ended:
                    isHovering = false
                }
            }
            .overlay {
                Rectangle()
                    .frame(width: 50, height: 50)
                    .foregroundColor(isHovering ? .green : .blue)
                    .offset(x: hoverLocation.x, y: hoverLocation.y)
            }
    }
}
```

## 获取悬停阶段

- **HoverPhase.active(_:)**：指针移动到视图内的指定位置。

- **HoverPhase.ended**：指针离开视图。

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移动到视图框架上方或下方时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制此视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。

## 符合以下规范

- BitwiseCopyable

- Copyable

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/HoverPhase
crawled: 2025-12-02T17:41:52Z
---

# HoverPhase

**Enumeration**

The current hovering state and value of the pointer.

## Declaration

```swift
@frozen enum HoverPhase
```

## Overview

When you use the [onContinuousHover(coordinateSpace:perform:)](View/onContinuousHover_coordinateSpace_perform.zh-Hans.md) modifier, you can handle the hovering state using the `action` closure. SwiftUI calls the closure with a phase value to indicate the current hovering state. The following example updates `hoverLocation` and `isHovering` based on the phase provided to the closure:

```swift
@State private var hoverLocation: CGPoint = .zero
@State private var isHovering = false

var body: some View {
    VStack {
        Color.red
            .frame(width: 400, height: 400)
            .onContinuousHover { phase in
                switch phase {
                case .active(let location):
                    hoverLocation = location
                    isHovering = true
                case .ended:
                    isHovering = false
                }
            }
            .overlay {
                Rectangle()
                    .frame(width: 50, height: 50)
                    .foregroundColor(isHovering ? .green : .blue)
                    .offset(x: hoverLocation.x, y: hoverLocation.y)
            }
    }
}
```

## Getting hover phases

- **HoverPhase.active(_:)**: The pointer’s location moved to the specified point within the view.
- **HoverPhase.ended**: The pointer exited the view.

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

