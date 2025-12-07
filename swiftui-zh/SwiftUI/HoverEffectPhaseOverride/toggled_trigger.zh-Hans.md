---
来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/toggled(触发器：)
抓取时间： 2025-12-03T06:45:08Z
---

# toggled(trigger:)

**类型方法**

立即过渡到与效果当前阶段相反的阶段。

## 声明

```swift
static func toggled(trigger: some Equatable) -> HoverEffectPhaseOverride
```

## 参数

- **trigger**：要观察变化的值。只要该值发生变化，覆盖就会重新应用。

## 讨论

应用此覆盖会使效果在应用覆盖时过渡到与其当前相位相反的相位。如果效果是 `active`，则相当于应用了 `inactive`覆盖（反之亦然）。悬停效果可以在应用程序进程之外应用，因此该覆盖允许在不需要知道当前阶段的情况下切换当前阶段。

`toggled`覆盖会在首次应用时改变特效的阶段，当给定的`Equatable`触发值发生变化时也会改变特效的阶段。这样就可以反复切换效果的相位。

当应用到一个组时，该组中的所有效果器都将受到影响（就像 `active` 或 `inactive` 重载一样）。对同一组中的多个效果应用覆盖是未定义的，因为不清楚应该应用哪个覆盖。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/toggled(trigger:)
crawled: 2025-12-03T06:45:08Z
---

# toggled(trigger:)

**Type Method**

Immediately transition to the opposite of an effect’s current phase.

## Declaration

```swift
static func toggled(trigger: some Equatable) -> HoverEffectPhaseOverride
```

## Parameters

- **trigger**: A value to observe for changes. The override will be reapplied whenever this value changes.

## Discussion

Applying this override causes an effect to transition to the opposite of its current phase at the moment the override is applied. If the effect is `active`, this is equivalent to applying the `inactive` override (and vice versa). Hover effects may be applied outside the app process, so this override allows the current phase to be toggled without needing to know the current phase.

The `toggled` override changes the effect’s phase when first applied, and also whenever the given `Equatable` trigger value changes. This allows the effect’s phase to be toggled repeatedly.

When applied to a group, all effects in the group will be affected (just like the `active` or `inactive` overrides). Applying overrides to multiple effects in the same group is undefined, due to it not being clear which override should be applied.

