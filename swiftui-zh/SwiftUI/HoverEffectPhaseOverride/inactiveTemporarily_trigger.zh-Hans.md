---
来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/inactiveTemporarily(触发器：)
抓取时间： 2025-12-01T11:34:22Z
---

# inactiveTemporarily(trigger:)

**类型方法**

暂时过渡到非激活阶段，直到所有动画结束，过渡完成。

## 声明

```swift
static func inactiveTemporarily(trigger: some Equatable) -> HoverEffectPhaseOverride
```

## 参数

- **trigger**：要观察变化的值。只要该值发生变化，覆盖就会重新应用。

## 讨论

使用 `inactiveTemporarily(trigger:)` 可以覆盖特效的阶段，直到它完全过渡到非激活阶段。该过渡将使用特效定义的动画，但会忽略任何延迟。

覆盖到期后，特效将再次响应悬停事件。如果视图没有悬停，特效将保持在非激活阶段。否则，它将开始过渡到激活阶段，并遵守特效上定义的任何延迟。

当应用到一个组时，该组中的所有特效也会变成非活动状态。对同一组中的多个效果应用覆盖是未定义的，因为不清楚应该应用哪个覆盖。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/inactiveTemporarily(trigger:)
crawled: 2025-12-01T11:34:22Z
---

# inactiveTemporarily(trigger:)

**Type Method**

Temporaily transitions to the inactve phase until all animations finish, and the transition is complete.

## Declaration

```swift
static func inactiveTemporarily(trigger: some Equatable) -> HoverEffectPhaseOverride
```

## Parameters

- **trigger**: A value to observe for changes. The override will be reapplied whenever this value changes.

## Discussion

Use `inactiveTemporarily(trigger:)` to override an effect’s phase until it fully transitions to its inactive phase. The transition will use the animations defined by the effect, but will ignore any delays.

When the override expires, the effect will respond to hover events again. If the view isn’t hovered, the effect will remain in the inactive phase. Otherwise it will begin transitioning to the active phase, honoring any delays defined on the effect.

When applied to a group, all effects in the group become inactive as well. Applying overrides to multiple effects in the same group is undefined, due to it not being clear which override should be applied.

