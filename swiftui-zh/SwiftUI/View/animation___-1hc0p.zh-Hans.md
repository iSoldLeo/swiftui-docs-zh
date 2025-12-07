--- 来源：https://developer.apple.com/documentation/SwiftUI/View/animation(_:)-1hc0p

抓取时间：2025-12-01T10:24:53Z

---

# animation(_:)

**实例方法**

将给定的动画应用于此视图中所有可动画的值。

## 声明

```swift
nonisolated func animation(_ animation: Animation?) -> some View

```

## 参数

- **animation**：要应用于此视图中可动画值的动画。

## 返回值

一个包装此视图并将 `animation` 应用于此视图中使用的所有可动画值的视图。

## 说明

在叶子视图上使用此修饰符，而不是容器视图。动画将应用于此视图中的所有子视图；对容器视图调用 `animation(_:)` 可能会导致作用域无界。


---
source: https://developer.apple.com/documentation/SwiftUI/View/animation(_:)-1hc0p
crawled: 2025-12-01T10:24:53Z
---

# animation(_:)

**Instance Method**

Applies the given animation to all animatable values within this view.

## Declaration

```swift
nonisolated func animation(_ animation: Animation?) -> some View

```

## Parameters

- **animation**: The animation to apply to animatable values within this view.

## Return Value

A view that wraps this view and applies `animation` to all animatable values used within the view.

## Discussion

Use this modifier on leaf views rather than container views. The animation applies to all child views within this view; calling `animation(_:)` on a container view can lead to unbounded scope.

