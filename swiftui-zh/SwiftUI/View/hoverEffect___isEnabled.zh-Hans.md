--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(_:isEnabled:)

抓取时间：2025-11-30T21:26:52Z

---

# hoverEffect(_:isEnabled:)

**实例方法**

为当前视图应用悬停效果。

## 声明

```swift
nonisolated func hoverEffect(_ effect: HoverEffect = .automatic, isEnabled: Bool = true) -> some View

```

## 参数

- **effect**：要应用到当前视图的效果。

- **isEnabled**：效果是否启用。

## 返回值

一个应用了悬停效果的新视图，该效果应用于 `self`。

## 说明

默认情况下，使用 [automatic](../HoverEffect/automatic.zh-Hans.md)。您可以使用 [defaultHoverEffect(_:)](defaultHoverEffect.zh-Hans.md) 修饰符控制自动效果的行为。

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移到视图框架上方或移出视图框架时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制此视图是否可以显示悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffect(_:isEnabled:)
crawled: 2025-11-30T21:26:52Z
---

# hoverEffect(_:isEnabled:)

**Instance Method**

Applies a hover effect to this view.

## Declaration

```swift
nonisolated func hoverEffect(_ effect: HoverEffect = .automatic, isEnabled: Bool = true) -> some View

```

## Parameters

- **effect**: The effect to apply to this view.
- **isEnabled**: Whether the effect is enabled or not.

## Return Value

A new view that applies a hover effect to `self`.

## Discussion

By default, [automatic](../HoverEffect/automatic.zh-Hans.md) is used. You can control the behavior of the automatic effect with the [defaultHoverEffect(_:)](defaultHoverEffect.zh-Hans.md) modifier.

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

