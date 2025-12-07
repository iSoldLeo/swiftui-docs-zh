--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectPhaseOverride(_:)

抓取时间：2025-12-03T06:45:40Z

---

# hoverEffectPhaseOverride(_:)

**实例方法**

返回一个应用了给定 `HoverEffectPhaseOverride` 的新效果。

## 声明

```swift
func hoverEffectPhaseOverride(_ override: HoverEffectPhaseOverride?) -> some CustomHoverEffect

```

## 参数

- **override**：要应用于悬停效果当前阶段的覆盖。如果提供了 `nil`，则此修饰符无效。

## 返回值

应用了给定覆盖的新效果。

## 讨论

例如，以下效果的透明度将*始终*为 1.0，因为覆盖设置会强制该效果始终处于激活状态：

```swift
Color.red
    .hoverEffect(
        .empty
        .hoverEffect { e, isActive, _ in
            e.opacity(isActive ? 1 : 0.5)
        }
        .hoverEffectPhaseOverride(.active)
    )
```

当应用于 `hoverEffectGroup` 时，覆盖设置将应用于组中的所有效果。以下示例中的两个视图的透明度都将为 1.0：

```swift
HStack {
    Color.red
        .hoverEffect(
            .empty
            .hoverEffect(in: hoverGroup) { e, isActive, _ in
                e.opacity(isActive ? 1 : 0.5)
            }
            .hoverEffectPhaseOverride(.active)
        )
    Color.red
        .hoverEffect(in: hoverGroup) { e, isActive, _ in
            e.opacity(isActive ? 1 : 0.5)
        }
```

}

将覆盖设置应用于同一组中的多个效果是未定义的，因为无法确定应该应用哪个覆盖设置。请选择组中的一个效果作为源效果（如上例所示），或者使用单独的 `.empty` 效果来应用覆盖设置：

```swift
Color.red
    .hoverEffect(
        // apply the override to an empty effect
        .empty
        .hoverEffectGroup(hoverGroup)
        .hoverEffectPhaseOverride(.active)
        // prevent hovering `Color.red` from triggering the group
        .hoverEffectDisabled(true)
    )
    .overlay {
        Rectangle()
            .strokeBorder()
            .hoverEffect(in: hoverGroup) { e, isActive, _ in
                e.opacity(isActive ? 1 : 0.5)
            }
    }
    .padding()
    .background {
        Color.blue
            .hoverEffect(in: hoverGroup) { e, isActive, _ in
                e.opacity(isActive ? 1 : 0.5)
            }
    }
```


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectPhaseOverride(_:)
crawled: 2025-12-03T06:45:40Z
---

# hoverEffectPhaseOverride(_:)

**Instance Method**

Returns a new effect with the given `HoverEffectPhaseOverride` applied to this effect.

## Declaration

```swift
func hoverEffectPhaseOverride(_ override: HoverEffectPhaseOverride?) -> some CustomHoverEffect

```

## Parameters

- **override**: The override to apply to the hover effect’s current phase. If `nil` is provided, this modifier has no effect.

## Return Value

A new effect with the given override applied.

## Discussion

For example, the following effect will *always* have an opacity of 1.0 since the override forces the effect to always be active:

```swift
Color.red
    .hoverEffect(
        .empty
        .hoverEffect { e, isActive, _ in
            e.opacity(isActive ? 1 : 0.5)
        }
        .hoverEffectPhaseOverride(.active)
    )
```

When applied to a `hoverEffectGroup` the override applies to all effects in the group. Both views in the following example will have an opacity of 1.0:

```swift
HStack {
    Color.red
        .hoverEffect(
            .empty
            .hoverEffect(in: hoverGroup) { e, isActive, _ in
                e.opacity(isActive ? 1 : 0.5)
            }
            .hoverEffectPhaseOverride(.active)
        )
    Color.red
        .hoverEffect(in: hoverGroup) { e, isActive, _ in
            e.opacity(isActive ? 1 : 0.5)
        }
```

}

Applying overrides to multiple effects in the same group is undefined, due to it not being clear which override should be applied. Choose one effect in the group to act as the source effect (as in the example above), or use a separate `.empty` effect to apply the override:

```swift
Color.red
    .hoverEffect(
        // apply the override to an empty effect
        .empty
        .hoverEffectGroup(hoverGroup)
        .hoverEffectPhaseOverride(.active)
        // prevent hovering `Color.red` from triggering the group
        .hoverEffectDisabled(true)
    )
    .overlay {
        Rectangle()
            .strokeBorder()
            .hoverEffect(in: hoverGroup) { e, isActive, _ in
                e.opacity(isActive ? 1 : 0.5)
            }
    }
    .padding()
    .background {
        Color.blue
            .hoverEffect(in: hoverGroup) { e, isActive, _ in
                e.opacity(isActive ? 1 : 0.5)
            }
    }
```

