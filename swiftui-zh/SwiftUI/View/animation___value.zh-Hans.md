--- 来源：https://developer.apple.com/documentation/SwiftUI/View/animation(_:value:)

抓取时间：2025-11-30T21:18:56Z

---

# animation(_:value:)

**实例方法**

当指定值发生变化时，将给定的动画应用于此视图。

## 声明

```swift
nonisolated func animation<V>(_ animation: Animation?, value: V) -> some View where V : Equatable

```

## 参数

- **animation**：要应用的动画。如果 `animation` 为 `nil`，则视图不会应用动画。

- **value**：要监视其变化的值。

## 返回值

当 `value` 发生变化时，将 `animation` 应用于此视图。

## 为视图添加基于状态的动画

- **animation(_:)**：当此视图发生变化时，将给定的动画应用于此视图。

- **animation(_:body:)**：将给定的动画应用于 `body` 闭包内的所有可动画值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/animation(_:value:)
crawled: 2025-11-30T21:18:56Z
---

# animation(_:value:)

**Instance Method**

Applies the given animation to this view when the specified value changes.

## Declaration

```swift
nonisolated func animation<V>(_ animation: Animation?, value: V) -> some View where V : Equatable

```

## Parameters

- **animation**: The animation to apply. If `animation` is `nil`, the view doesn’t animate.
- **value**: A value to monitor for changes.

## Return Value

A view that applies `animation` to this view whenever `value` changes.

## Adding state-based animation to a view

- **animation(_:)**: Applies the given animation to this view when this view changes.
- **animation(_:body:)**: Applies the given animation to all animatable values within the `body` closure.

