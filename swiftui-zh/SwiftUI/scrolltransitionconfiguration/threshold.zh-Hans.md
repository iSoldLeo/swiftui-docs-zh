--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/threshold(_:)

抓取时间：2025-12-03T06:42:48Z

---

# threshold(_:)

**实例方法**

设置视图完全可见的阈值。

## 声明

```swift
func threshold(_ threshold: ScrollTransitionConfiguration.Threshold) -> ScrollTransitionConfiguration
```

## 参数

- **threshold**：指定视图与容器重叠多少才能被视为可见的阈值。

## 返回值

此配置的副本，阈值设置为给定值。

## 访问配置

- **animation(_:)**：设置过渡动画。

- **ScrollTransitionConfiguration.Threshold**：描述容器内目标视图从隐藏（完全位于容器外部）到可见的特定变化过程。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTransitionConfiguration/threshold(_:)
crawled: 2025-12-03T06:42:48Z
---

# threshold(_:)

**Instance Method**

Sets the threshold at which the view will be considered fully visible.

## Declaration

```swift
func threshold(_ threshold: ScrollTransitionConfiguration.Threshold) -> ScrollTransitionConfiguration
```

## Parameters

- **threshold**: The threshold specifying how much of the view must intersect with the container before it is treated as visible.

## Return Value

A copy of this configuration with the threshold set to the given value.

## Accessing the configuration

- **animation(_:)**: Sets the animation with which the transition will be applied.
- **ScrollTransitionConfiguration.Threshold**: Describes a specific point in the progression of a target view within a container from hidden (fully outside the container) to visible.

