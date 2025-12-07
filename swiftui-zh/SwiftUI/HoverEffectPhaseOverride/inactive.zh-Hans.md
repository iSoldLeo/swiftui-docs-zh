---
来源： https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/inactive
抓取时间： 2025-12-03T06:45:06Z
---

# 不活动

**类型属性**

立即过渡到非激活阶段。

## 声明

```swift
static var inactive: HoverEffectPhaseOverride { get }
```

## 讨论

无论视图是否悬停，应用此覆盖都会使特效立即处于非活动状态。过渡将使用特效定义的动画，但会忽略任何延迟。在移除此覆盖之前，效果将一直处于非激活状态。

当应用到一个组时，该组中的所有特效也将处于非激活状态。对同一组中的多个特效应用覆盖是未定义的，因为不清楚应该应用哪个覆盖。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/inactive
crawled: 2025-12-03T06:45:06Z
---

# inactive

**Type Property**

Immediately transition to the inactive phase.

## Declaration

```swift
static var inactive: HoverEffectPhaseOverride { get }
```

## Discussion

Applying this override causes an effect to become inactive immediately, regardless of whether the view is hovered or not. The transition will use the animations defined by the effect, but will ignore any delays. The effect remains inactive until this override is removed.

When applied to a group, all effects in the group become inactive as well. Applying overrides to multiple effects in the same group is undefined, due to it not being clear which override should be applied.

