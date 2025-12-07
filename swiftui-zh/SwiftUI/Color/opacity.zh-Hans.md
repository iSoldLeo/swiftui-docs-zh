---
来源： https://developer.apple.com/documentation/SwiftUI/Color/opacity(_:)
抓取时间： 2025-12-01T10:29:01Z
---

# 不透明度(_:)

**实例方法**

将颜色的不透明度乘以给定的数值。

## 声明

```swift
func opacity(_ opacity: Double) -> Color
```

## 参数

- **opacity**：颜色不透明度的乘积。

## 返回值

已修改不透明度的视图。

## 修改颜色

- **gradient**：返回颜色 `self` 的标准渐变。
- **mix(with:by:in:)**：返回按 `fraction` 指定的数量与 `rhs` 混合的 self 版本。
- **exposureAdjust(_:)**：返回已应用曝光调整的新颜色。
- **headroom(_:)**：创建具有指定 HDR 内容余量的新颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/opacity(_:)
crawled: 2025-12-01T10:29:01Z
---

# opacity(_:)

**Instance Method**

Multiplies the opacity of the color by the given amount.

## Declaration

```swift
func opacity(_ opacity: Double) -> Color
```

## Parameters

- **opacity**: The amount by which to multiply the opacity of the color.

## Return Value

A view with modified opacity.

## Modifying a color

- **gradient**: Returns the standard gradient for the color `self`.
- **mix(with:by:in:)**: Returns a version of self mixed with `rhs` by the amount specified by `fraction`.
- **exposureAdjust(_:)**: Returns a new color with an exposure adjustment applied.
- **headroom(_:)**: Creates a new color with specified HDR content headroom.

