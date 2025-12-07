--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup/systemOverlays
抓取时间：2025-12-03T06:45:49Z

---

# systemOverlays

**类型属性**

当系统叠加层可见时，此属性会激活。

## 声明

```swift
static var systemOverlays: HoverEffectGroup { get }
```

## 说明

使用此组可将效果与系统叠加层同步。在以下示例中，当系统叠加层隐藏时，返回按钮也会隐藏。

```swift
Button("Back") { }
    .hoverEffect(in: .systemOverlays) { e, isActive, _ in
        e.animation(
            isActive ? .systemOverlayAppearance : .systemOverlayDelayedDisappearance
        ) {
            $0.opacity(isActive ? 1 : 0)
        }
    }
    .persistentSystemOverlays(.hidden)
```

此示例使用 `systemOverlayAppearance` 和 `systemOverlayDisappearance` 动画，以确保效果与系统叠加层的动画同步。

如果 `persistentSystemOverlays` 不等于 `.hidden`，则此群组将始终处于活动状态。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup/systemOverlays
crawled: 2025-12-03T06:45:49Z
---

# systemOverlays

**Type Property**

A `HoverEffectGroup` that becomes active when system overlays are visible.

## Declaration

```swift
static var systemOverlays: HoverEffectGroup { get }
```

## Discussion

Use this group to synchronize effects with system overlays. In the following example, the back button will be hidden whenever system overlays are hidden.

```swift
Button("Back") { }
    .hoverEffect(in: .systemOverlays) { e, isActive, _ in
        e.animation(
            isActive ? .systemOverlayAppearance : .systemOverlayDelayedDisappearance
        ) {
            $0.opacity(isActive ? 1 : 0)
        }
    }
    .persistentSystemOverlays(.hidden)
```

This example uses the `systemOverlayAppearance` and `systemOverlayDisappearance` animations to ensure the effect using the same timing as system overlays.

If `persistentSystemOverlays` is not `.hidden`, this group will always be active.

