--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectDisabled(_:)

抓取时间：2025-12-01T11:34:46Z

---

# hoverEffectDisabled(_:)

**实例方法**

禁用此悬停效果。

## 声明

```swift
func hoverEffectDisabled(_ isDisabled: Bool = true) -> some CustomHoverEffect

```

## 参数

- **isDisabled**：一个布尔值，用于确定是否禁用悬停效果。指定 `true` 的优先级高于 `false`。默认值：`true`。

## 返回值

一个条件性禁用的悬停效果。

## 讨论

使用 `hoverEffectDisabled(_:)` 可阻止悬停效果激活。禁用效果后，其包含的所有效果也会被禁用且无法重新启用。

在以下示例中，如果启用 `accessibilityReduceMotion` 设置，则缩放效果将被禁用：

```swift
struct ScaleAndFadeEffect: CustomHoverEffect {
    @Environment(\.accessibilityReduceMotion) var accessibilityReduceMotion
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, _ in
            effect.scaleEffect(!isActive ? 0.95 : 1.05)
        }
        .hoverEffectDisabled(accessibilityReduceMotion)
        .hoverEffect { effect, isActive, _ in
            effect.opacity(!isActive ? 0.9 : 1)
        }
    }
}
```

## 创建自定义悬停效果

- **hoverEffect(_:in:isEnabled:)**：将此效果与给定的 `effect` 并行应用。

- **hoverEffect(in:isEnabled:body:)**：应用基于当前阶段的悬停效果。

- **hoverEffectGroup(_:)**：将此效果作为效果组的一部分激活。

- **hoverEffectGroup(id:in:behavior:)**：将此效果作为效果组的一部分激活。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectDisabled(_:)
crawled: 2025-12-01T11:34:46Z
---

# hoverEffectDisabled(_:)

**Instance Method**

Disables this hover effect.

## Declaration

```swift
func hoverEffectDisabled(_ isDisabled: Bool = true) -> some CustomHoverEffect

```

## Parameters

- **isDisabled**: A Boolean value that determines whether the hover effect is disabled or not. Specifying `true` takes precedence over `false`. Default: `true`.

## Return Value

A conditionally disabled hover effect.

## Discussion

Use `hoverEffectDisabled(_:)` to prevent a hover effect from becoming active. When an effect is disabled, all contained effects are also disabled and cannot be re-enabled.

In the following example, the scale effect is disabled if the `accessibilityReduceMotion` setting is enabled:

```swift
struct ScaleAndFadeEffect: CustomHoverEffect {
    @Environment(\.accessibilityReduceMotion) var accessibilityReduceMotion
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, _ in
            effect.scaleEffect(!isActive ? 0.95 : 1.05)
        }
        .hoverEffectDisabled(accessibilityReduceMotion)
        .hoverEffect { effect, isActive, _ in
            effect.opacity(!isActive ? 0.9 : 1)
        }
    }
}
```

## Creating custom hover effects

- **hoverEffect(_:in:isEnabled:)**: Applies this effect in parallel with the given `effect`.
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect based on the current phase.
- **hoverEffectGroup(_:)**: Activates this effect as part of an effect group.
- **hoverEffectGroup(id:in:behavior:)**: Activates this effect as part of an effect group.

