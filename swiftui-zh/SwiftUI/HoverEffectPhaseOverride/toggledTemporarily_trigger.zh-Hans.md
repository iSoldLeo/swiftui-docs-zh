---
来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/toggledTemporarily(触发器：)
抓取时间： 2025-12-01T11:34:23Z
---

# toggledTemporarily(trigger:)

**类型方法**

在应用覆盖时，暂时过渡到与效果当前相位相反的相位。

## 声明

```swift
static func toggledTemporarily(trigger: some Equatable) -> HoverEffectPhaseOverride
```

## 参数

- **trigger**：要观察变化的值。只要该值发生变化，覆盖就会重新应用。

## 讨论

使用 `toggledTemporarily(trigger:)` 可以切换特效的当前阶段，直到它完全过渡到新阶段。过渡将使用特效定义的动画，但忽略任何延迟。

覆盖到期后，特效将再次响应悬停事件。如果视图被悬停，特效将过渡到激活阶段，否则将过渡到非激活阶段。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectPhaseOverride/toggledTemporarily(trigger:)
crawled: 2025-12-01T11:34:23Z
---

# toggledTemporarily(trigger:)

**Type Method**

Temporaily transitions to the opposite of the effect’s current phase at the moment the override is applied.

## Declaration

```swift
static func toggledTemporarily(trigger: some Equatable) -> HoverEffectPhaseOverride
```

## Parameters

- **trigger**: A value to observe for changes. The override will be reapplied whenever this value changes.

## Discussion

Use `toggledTemporarily(trigger:)` to toggle an effect’s current phase until it fully transitions to its new phase. The transition will use the animations defined by the effect, but will ignore any delays.

When the override expires, the effect will respond to hover events again. If the view is hovered, the effect will transition to it’s active phase, otherwise its inactive phase.

