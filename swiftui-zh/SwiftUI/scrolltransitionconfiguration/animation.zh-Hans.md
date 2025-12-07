--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/animation(_:)

抓取时间：2025-12-01T11:32:05Z

---

# animation(_:)

**实例方法**

设置过渡动画。

## 声明

```swift
func animation(_ animation: Animation) -> ScrollTransitionConfiguration
```

## 参数

- **animation**：用于将过渡动画应用于视图的动画。

## 返回值

此配置的副本，动画已设置为给定值。

## 说明

如果过渡是交互式的，则给定的动画将用于使效果向当前插值值移动，导致效果滞后于当前滚动位置。

## 访问配置

- **threshold(_:)**：设置视图完全可见的阈值。

- **ScrollTransitionConfiguration.Threshold**：描述目标视图在容器内从隐藏（完全位于容器外部）到可见的特定状态变化过程。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/animation(_:)
crawled: 2025-12-01T11:32:05Z
---

# animation(_:)

**Instance Method**

Sets the animation with which the transition will be applied.

## Declaration

```swift
func animation(_ animation: Animation) -> ScrollTransitionConfiguration
```

## Parameters

- **animation**: An animation that will be used to apply the transition to the view.

## Return Value

A copy of this configuration with the animation set to the given value.

## Discussion

If the transition is interactive, the given animation will be used to animate the effect toward the current interpolated value, causing the effect to lag behind the current scroll position.

## Accessing the configuration

- **threshold(_:)**: Sets the threshold at which the view will be considered fully visible.
- **ScrollTransitionConfiguration.Threshold**: Describes a specific point in the progression of a target view within a container from hidden (fully outside the container) to visible.

