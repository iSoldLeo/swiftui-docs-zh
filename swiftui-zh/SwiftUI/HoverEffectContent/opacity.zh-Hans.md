--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/opacity(_:)

抓取时间：2025-12-01T11:35:02Z

---

# opacity(_:)

**实例方法**

设置视图的透明度。

## 声明

```swift
func opacity(_ opacity: Double) -> some HoverEffectContent

```

## 参数

- **opacity**：介于 0（完全透明）和 1（完全不透明）之间的值。

## 返回值

设置视图透明度的效果。

## 说明

当将 `opacity(_:)` 效果应用于已进行过透明度变换的视图时，底层透明度变换的效果会叠加。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/opacity(_:)
crawled: 2025-12-01T11:35:02Z
---

# opacity(_:)

**Instance Method**

Sets the transparency of the view.

## Declaration

```swift
func opacity(_ opacity: Double) -> some HoverEffectContent

```

## Parameters

- **opacity**: A value between 0 (fully transparent) and 1 (fully opaque).

## Return Value

An effect that sets the transparency of the view.

## Discussion

When applying the `opacity(_:)` effect to a view that has already had its opacity transformed, the effect of the underlying opacity transformation is multiplied.

