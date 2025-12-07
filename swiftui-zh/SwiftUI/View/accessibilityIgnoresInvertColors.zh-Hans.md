--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityIgnoresInvertColors(_:)

抓取时间：2025-11-30T21:28:35Z

---

# accessibilityIgnoresInvertColors(_:)

**实例方法**

设置此视图是否应忽略系统智能反转设置。

## 声明

```swift
nonisolated func accessibilityIgnoresInvertColors(_ active: Bool = true) -> some View

```

## 参数

- **active**：值为 true 时忽略系统智能反转设置。值为 false 时遵循系统设置。

## 说明

使用此修饰符可以禁用不应反转的视图中的智能反转。或者，传递 `active` 参数或 `false` 参数，以便在之前禁用智能反转设置的情况下重新启用它。

## 管理颜色

- **accessibilityInvertColors**：是否启用“反转颜色”系统偏好设置。

- **accessibilityDifferentiateWithoutColor**：是否启用“无颜色区分”系统偏好设置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityIgnoresInvertColors(_:)
crawled: 2025-11-30T21:28:35Z
---

# accessibilityIgnoresInvertColors(_:)

**Instance Method**

Sets whether this view should ignore the system Smart Invert setting.

## Declaration

```swift
nonisolated func accessibilityIgnoresInvertColors(_ active: Bool = true) -> some View

```

## Parameters

- **active**: A true value ignores the system Smart Invert setting. A false value follows the system setting.

## Discussion

Use this modifier to suppress Smart Invert in a view that shouldn’t be inverted. Or pass an `active` argument of `false` to begin following the Smart Invert setting again when it was previously disabled.

## Managing color

- **accessibilityInvertColors**: Whether the system preference for Invert Colors is enabled.
- **accessibilityDifferentiateWithoutColor**: Whether the system preference for Differentiate without Color is enabled.

