--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffect(_:in:isEnabled:)

抓取时间：2025-12-01T11:34:43Z
---

# hoverEffect(_:in:isEnabled:)

**实例方法**

将此效果与给定的 `effect` 并行应用。

## 声明

```swift
func hoverEffect(_ effect: some CustomHoverEffect, in group: HoverEffectGroup? = nil, isEnabled: Bool = true) -> some CustomHoverEffect

```

## 参数

- **effect**：要与此效果结合的 [CustomHoverEffect](../CustomHoverEffect.zh-Hans.md)。

- **group**：可选的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，用于添加此效果。

- **isEnabled**：`effect` 是否启用。

## 讨论

使用 `hoverEffect(_:)` 将两个效果合并为一个并行应用的效果。应用于 `effect` 的修饰符（例如 [hoverEffectDisabled(_:)](hoverEffectDisabled.zh-Hans.md)）不会影响此效果。

例如，在以下效果中，仅禁用了 `ScaleUpEffect`，因为应用于该效果的修饰符是独立应用的。

```swift
struct FadeAndScaleEffect: CustomHoverEffect {
    @Environment(\.accessibilityReduceMotion) var accessibilityReduceMotion
    func body(content: Content) -> some CustomHoverEffect {
        content
            .hoverEffect { effect, isActive, _ in
                effect.opacity(isActive ? 1 : 0.9)
            }
            .hoverEffect(
                ScaleUpEffect().hoverEffectDisabled(accessibilityReduceMotion)
            )
    }
}

struct ScaleUpEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, _ in
            effect.scaleEffect(isActive ? 1.05 : 1.0)
        }
    }
}
```

- 返回一个并行应用两个效果的新效果。

## 创建自定义悬停效果

- **hoverEffect(in:isEnabled:body:)**：根据当前阶段应用悬停效果。

- **hoverEffectGroup(_:)**：将此效果作为效果组的一部分激活。

- **hoverEffectGroup(id:in:behavior:)**：将此效果作为效果组的一部分激活。

- **hoverEffectDisabled(_:)**：禁用此悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffect(_:in:isEnabled:)
crawled: 2025-12-01T11:34:43Z
---

# hoverEffect(_:in:isEnabled:)

**Instance Method**

Applies this effect in parallel with the given `effect`.

## Declaration

```swift
func hoverEffect(_ effect: some CustomHoverEffect, in group: HoverEffectGroup? = nil, isEnabled: Bool = true) -> some CustomHoverEffect

```

## Parameters

- **effect**: A [CustomHoverEffect](../CustomHoverEffect.zh-Hans.md) to combine with this effect.
- **group**: An optional [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to add this effect to.
- **isEnabled**: Whether `effect` is enabled or not.

## Discussion

Use `hoverEffect(_:)` to combine two effects into a single effect that applies both effects in parallel. Modifiers like [hoverEffectDisabled(_:)](hoverEffectDisabled.zh-Hans.md) applied to `effect` will not apply to this effect.

For example, in the following effect only the `ScaleUpEffect` is disabled, since modifiers applied to that effect are applied independently.

```swift
struct FadeAndScaleEffect: CustomHoverEffect {
    @Environment(\.accessibilityReduceMotion) var accessibilityReduceMotion
    func body(content: Content) -> some CustomHoverEffect {
        content
            .hoverEffect { effect, isActive, _ in
                effect.opacity(isActive ? 1 : 0.9)
            }
            .hoverEffect(
                ScaleUpEffect().hoverEffectDisabled(accessibilityReduceMotion)
            )
    }
}

struct ScaleUpEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, _ in
            effect.scaleEffect(isActive ? 1.05 : 1.0)
        }
    }
}
```

- Returns a new effect that applies both effects in parallel.

## Creating custom hover effects

- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect based on the current phase.
- **hoverEffectGroup(_:)**: Activates this effect as part of an effect group.
- **hoverEffectGroup(id:in:behavior:)**: Activates this effect as part of an effect group.
- **hoverEffectDisabled(_:)**: Disables this hover effect.

