---
来源： https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/active
抓取时间：2025-12-03T06:45:05Z
---

# 活跃

**类型属性**

立即过渡到激活阶段。

## 声明

```swift
static var active: HoverEffectPhaseOverride { get }
```

## 讨论

无论视图是否悬停，应用此覆盖项都会使悬停效果立即激活。过渡将使用效果所定义的动画，但会忽略任何延迟。在移除此覆盖之前，该效果一直处于激活状态。

当应用到一个组时，该组中的所有特效也将处于激活状态。对同一组中的多个特效应用覆盖是未定义的，因为不清楚应该应用哪个覆盖。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/active
crawled: 2025-12-03T06:45:05Z
---

# active

**Type Property**

Immediately transition to the active phase.

## Declaration

```swift
static var active: HoverEffectPhaseOverride { get }
```

## Discussion

Applying this override causes a hover effect to become active immediately, regardless of whether the view is hovered or not. The transition will use the animations defined by the effect, but will ignore any delays. The effect remains active until this override is removed.

When applied to a group, all effects in the group become active as well. Applying overrides to multiple effects in the same group is undefined, due to it not being clear which override should be applied.

