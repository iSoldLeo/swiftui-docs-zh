--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onHover(perform:)

抓取时间：2025-11-30T21:26:50Z

---

# onHover(perform:)

**实例方法**

添加一个当用户将指针移至视图框架上方或下方时要执行的操作。

## 声明

```swift
nonisolated func onHover(perform action: @escaping (Bool) -> Void) -> some View

```

## 参数

- **action**：指针进入或离开此视图框架时要执行的操作。如果指针位于视图框架内，则闭包 `action` 会将 `true` 作为参数传递；否则，传递 `false`。

## 返回值

当指针进入或离开此视图的框架时，会触发 `action` 的视图。

## 说明

调用此方法会定义一个用于检测指针移动的区域，该区域的大小和位置与此视图相同。

## 响应悬停事件

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、在视图边界内移动或离开视图边界时执行该操作。

- **hoverEffect(_:isEnabled:)**：为此视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制此视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onHover(perform:)
crawled: 2025-11-30T21:26:50Z
---

# onHover(perform:)

**Instance Method**

Adds an action to perform when the user moves the pointer over or away from the view’s frame.

## Declaration

```swift
nonisolated func onHover(perform action: @escaping (Bool) -> Void) -> some View

```

## Parameters

- **action**: The action to perform whenever the pointer enters or exits this view’s frame. If the pointer is in the view’s frame, the `action` closure passes `true` as a parameter; otherwise, `false`.

## Return Value

A view that triggers `action` when the pointer enters or exits this view’s frame.

## Discussion

Calling this method defines a region for detecting pointer movement with the size and position of this view.

## Responding to hover events

- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

