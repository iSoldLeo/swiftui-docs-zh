---
来源：https://developer.apple.com/documentation/SwiftUI/Color/mix(with:by:in:)
抓取时间：2025-12-01T10:29:03Z
---

# mix(with:by:in:)

**实例方法**

返回按 `fraction` 指定的数量与 `rhs` 混合的 self 版本。

## 声明

```swift
func mix(with rhs: Color, by fraction: Double, in colorSpace: Gradient.ColorSpace = .perceptual) -> Color
```

## 参数

- **rhs**：要与`self` 混合的颜色。
- **fraction**：混合量，`0.5` 表示 `self` 与 `rhs` 等量混合。
- **colorSpace**：用于混合颜色的色彩空间。

## 返回值

基于 `self` 和 `rhs` 的新 `Color`。

## 修改颜色

- **opacity(_:)**：将颜色的不透明度乘以给定的数值。
- **gradient**：返回颜色 `self` 的标准渐变效果。
- **exposureAdjust(_:)**：返回已应用曝光调整的新颜色。
- **headroom(_:)**：创建具有指定 HDR 内容余量的新颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/mix(with:by:in:)
crawled: 2025-12-01T10:29:03Z
---

# mix(with:by:in:)

**Instance Method**

Returns a version of self mixed with `rhs` by the amount specified by `fraction`.

## Declaration

```swift
func mix(with rhs: Color, by fraction: Double, in colorSpace: Gradient.ColorSpace = .perceptual) -> Color
```

## Parameters

- **rhs**: The color to mix `self` with.
- **fraction**: The amount of blending, `0.5` means `self` is mixed in equal parts with `rhs`.
- **colorSpace**: The color space used to mix the colors.

## Return Value

A new `Color` based on `self` and `rhs`.

## Modifying a color

- **opacity(_:)**: Multiplies the opacity of the color by the given amount.
- **gradient**: Returns the standard gradient for the color `self`.
- **exposureAdjust(_:)**: Returns a new color with an exposure adjustment applied.
- **headroom(_:)**: Creates a new color with specified HDR content headroom.

