--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusEffectDisabled(_:)

抓取时间：2025-11-30T21:28:20Z

---

# focusEffectDisabled(_:)

**实例方法**

添加一个条件，用于控制此视图是否可以显示焦点效果，例如默认的焦点环或悬停效果。

## 声明

```swift
nonisolated func focusEffectDisabled(_ disabled: Bool = true) -> some View

```

## 参数

- **disabled**：一个布尔值，用于确定此视图是否可以显示焦点效果。

## 返回值

一个用于控制此视图中是否显示焦点效果的视图。

## 说明

视图层次结构中更高级别的视图可以覆盖您在此视图中设置的值。在以下示例中，按钮未显示聚焦效果，因为外部的 `focusEffectDisabled(_:)` 修饰符覆盖了内部的修饰符：

```swift
HStack {
    Button("Press") {}
        .focusEffectDisabled(false)
}
.focusEffectDisabled(true)
```

## 配置效果

- **isFocusEffectEnabled**：一个布尔值，指示与此环境关联的视图是否允许显示聚焦效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusEffectDisabled(_:)
crawled: 2025-11-30T21:28:20Z
---

# focusEffectDisabled(_:)

**Instance Method**

Adds a condition that controls whether this view can display focus effects, such as a default focus ring or hover effect.

## Declaration

```swift
nonisolated func focusEffectDisabled(_ disabled: Bool = true) -> some View

```

## Parameters

- **disabled**: A Boolean value that determines whether this view can display focus effects.

## Return Value

A view that controls whether focus effects can be displayed in this view.

## Discussion

The higher views in a view hierarchy can override the value you set on this view. In the following example, the button does not display a focus effect because the outer `focusEffectDisabled(_:)` modifier overrides the inner one:

```swift
HStack {
    Button("Press") {}
        .focusEffectDisabled(false)
}
.focusEffectDisabled(true)
```

## Configuring effects

- **isFocusEffectEnabled**: A Boolean value that indicates whether the view associated with this environment allows focus effects to be displayed.

