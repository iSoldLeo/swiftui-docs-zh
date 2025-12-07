--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultHoverEffect(_:)

抓取时间：2025-11-30T21:26:54Z

---

# defaultHoverEffect(_:)

**实例方法**

设置此视图内所有视图的默认悬停效果。

## 声明

```swift
nonisolated func defaultHoverEffect(_ effect: HoverEffect?) -> some View

```

## 参数

- **effect**：此视图内所有视图的默认悬停效果。

## 返回值

使用此效果作为默认悬停效果的视图。

## 说明

使用此修饰符可为视图内所有应用了 [hoverEffect(_:)](hoverEffect.zh-Hans.md) 修饰符的视图设置特定的悬停效果。当未提供 [HoverEffect](../HoverEffect.zh-Hans.md) 或指定了 [automatic](../HoverEffect/automatic.zh-Hans.md) 时，通常使用默认效果。

例如，此视图对红色和绿色颜色视图都使用了 [highlight](../HoverEffect/highlight.zh-Hans.md)：

```swift
HStack {
    Color.red.hoverEffect()
    Color.green.hoverEffect()
}
.defaultHoverEffect(.highlight)
```

当使用 SwiftUI 定义的样式（例如 `ButtonStyle/bordered`）时，此方法也适用于自定义视图（例如 [Button](../Button.zh-Hans.md)）的默认悬停效果，因为 SwiftUI 定义的样式默认会提供悬停效果。例如，此视图将 [Button](../Button.zh-Hans.md) 的悬停效果替换为 [highlight](../HoverEffect/highlight.zh-Hans.md)：

```swift
Button("Next") {}
    // perform action
}
.buttonStyle(.bordered)
.defaultHoverEffect(.highlight)
```

使用 `nil` 效果表示不应修改默认悬停效果。

## 响应悬停事件

- **onHover(perform:)**：当用户将指针移至视图框架上方或移出时，添加要执行的操作。

- **onContinuousHover(coordinateSpace:perform:)**：当指针进入、移动到视图边界内以及离开视图边界时，添加要执行的操作。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **hoverEffectDisabled(_:)**：添加一个条件，用于控制该视图是否可以显示悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultHoverEffect(_:)
crawled: 2025-11-30T21:26:54Z
---

# defaultHoverEffect(_:)

**Instance Method**

Sets the default hover effect to use for views within this view.

## Declaration

```swift
nonisolated func defaultHoverEffect(_ effect: HoverEffect?) -> some View

```

## Parameters

- **effect**: The default hover effect to use for views within this view.

## Return Value

A view that uses this effect as the default hover effect.

## Discussion

Use this modifier to set a specific hover effect for all views with the [hoverEffect(_:)](hoverEffect.zh-Hans.md) modifier applied within a view. The default effect is typically used when no [HoverEffect](../HoverEffect.zh-Hans.md) was provided or if [automatic](../HoverEffect/automatic.zh-Hans.md) is specified.

For example, this view uses [highlight](../HoverEffect/highlight.zh-Hans.md) for both the red and green Color views:

```swift
HStack {
    Color.red.hoverEffect()
    Color.green.hoverEffect()
}
.defaultHoverEffect(.highlight)
```

This also works for customizing the default hover effect in views like [Button](../Button.zh-Hans.md)s when using a SwiftUI-defined style like `ButtonStyle/bordered`, which can provide a hover effect by default. For example, this view replaces the hover effect for a [Button](../Button.zh-Hans.md) with [highlight](../HoverEffect/highlight.zh-Hans.md):

```swift
Button("Next") {}
    // perform action
}
.buttonStyle(.bordered)
.defaultHoverEffect(.highlight)
```

Use a `nil` effect to indicate that the default hover effect should not be modified.

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **hoverEffectDisabled(_:)**: Adds a condition that controls whether this view can display hover effects.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

