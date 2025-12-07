--- 来源：https://developer.apple.com/documentation/SwiftUI/View/animation(_:)

抓取时间：2025-11-30T21:18:55Z

---

# animation(_:)

**实例方法**

当此视图发生变化时，应用指定的动画。

## 声明

```swift
nonisolated func animation(_ animation: Animation?) -> some View

```

## 参数

- **animation**：要应用的动画。如果 `animation` 为 `nil`，则视图不应用动画。

## 返回值

一个视图，当此视图发生变化时，应用 `animation` 后，该视图将生效。

## 为视图添加基于状态的动画

- **animation(_:value:)**：当指定值发生变化时，将给定的动画应用于此视图。

- **animation(_:body:)**：将给定的动画应用于 `body` 闭包内的所有可动画值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/animation(_:)
crawled: 2025-11-30T21:18:55Z
---

# animation(_:)

**Instance Method**

Applies the given animation to this view when this view changes.

## Declaration

```swift
nonisolated func animation(_ animation: Animation?) -> some View

```

## Parameters

- **animation**: The animation to apply. If `animation` is `nil`, the view doesn’t animate.

## Return Value

A view that applies `animation` to this view whenever it changes.

## Adding state-based animation to a view

- **animation(_:value:)**: Applies the given animation to this view when the specified value changes.
- **animation(_:body:)**: Applies the given animation to all animatable values within the `body` closure.

