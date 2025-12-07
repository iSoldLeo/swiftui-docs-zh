--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffectDisabled(_:)

抓取时间：2025-11-30T21:26:53Z

---

# hoverEffectDisabled(_:)

**实例方法**

添加一个条件，用于控制此视图是否可以显示悬停效果。

## 声明

```swift
nonisolated func hoverEffectDisabled(_ disabled: Bool = true) -> some View

```

## 参数

- **disabled**：一个布尔值，用于确定此视图是否可以显示悬停效果。

## 返回值

一个用于控制此视图中是否显示悬停效果的视图。

## 说明

视图层次结构中更高级别的视图可以覆盖您在此视图中设置的值。在以下示例中，按钮不显示悬停效果，因为外部的 `hoverEffectDisabled(_:)` 修饰符覆盖了内部的修饰符：

```swift
HStack {
    Button("Press") {}
        .hoverEffectDisabled(false)
}
.hoverEffectDisabled(true)
```

## 响应悬停事件

- **onHover(perform:)**：添加一个操作，当用户将指针移到视图框架上方或下方时执行。

- **onContinuousHover(coordinateSpace:perform:)**：添加一个操作，当指针进入、移动到视图边界内以及离开视图边界时执行。

- **hoverEffect(_:isEnabled:)**：为该视图应用悬停效果。

- **defaultHoverEffect(_:)**：设置此视图内其他视图使用的默认悬停效果。

- **isHoverEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示悬停效果。

- **HoverPhase**：指针的当前悬停状态和值。

- **HoverEffectPhaseOverride**：用于覆盖悬停效果当前阶段的选项。

- **OrnamentHoverContentEffect**：使用自定义效果在悬停时显示装饰物。

- **OrnamentHoverEffect**：在悬停时显示装饰物。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffectDisabled(_:)
crawled: 2025-11-30T21:26:53Z
---

# hoverEffectDisabled(_:)

**Instance Method**

Adds a condition that controls whether this view can display hover effects.

## Declaration

```swift
nonisolated func hoverEffectDisabled(_ disabled: Bool = true) -> some View

```

## Parameters

- **disabled**: A Boolean value that determines whether this view can display hover effects.

## Return Value

A view that controls whether hover effects can be displayed in this view.

## Discussion

The higher views in a view hierarchy can override the value you set on this view. In the following example, the button does not display a hover effect because the outer `hoverEffectDisabled(_:)` modifier overrides the inner one:

```swift
HStack {
    Button("Press") {}
        .hoverEffectDisabled(false)
}
.hoverEffectDisabled(true)
```

## Responding to hover events

- **onHover(perform:)**: Adds an action to perform when the user moves the pointer over or away from the view’s frame.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.
- **hoverEffect(_:isEnabled:)**: Applies a hover effect to this view.
- **defaultHoverEffect(_:)**: Sets the default hover effect to use for views within this view.
- **isHoverEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows hover effects to be displayed.
- **HoverPhase**: The current hovering state and value of the pointer.
- **HoverEffectPhaseOverride**: Options for overriding a hover effect’s current phase.
- **OrnamentHoverContentEffect**: Presents an ornament on hover using a custom effect.
- **OrnamentHoverEffect**: Presents an ornament on hover.

