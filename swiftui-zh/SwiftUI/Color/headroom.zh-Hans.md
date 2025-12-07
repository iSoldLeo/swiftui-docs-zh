---
来源： https://developer.apple.com/documentation/SwiftUI/Color/headroom(_:)
抓取时间： 2025-12-03T05:39:56Z
---

# headroom(_:)

**实例方法**

创建具有指定 HDR 内容净空的新颜色。

## 声明

```swift
func headroom(_ headroom: Double?) -> Color
```

## 参数

- **headroom**：要与新颜色关联的净空值。

## 返回值

具有指定净空值的新颜色。

## 讨论

高动态范围颜色（RGB 分量超出标准 [0, 1] 范围的颜色）应标注净空，以确保正确显示。了解内容余量可让渲染系统在显示颜色时自动增加显示余量，并在可用显示余量不足以按预期渲染颜色时对颜色进行色调映射。

例如，自定义黄色的亮度增加了两个曝光级别：

```swift
Color(.sRGB, red: 1.83, green: 1.47, blue: 0)
    .headroom(4)
```

请注意，净空是一个线性量，因此任何色彩调整通常都应在线性色彩空间中进行。

## 修改颜色

- **opacity(_:)**：将颜色的不透明度乘以给定的数值。
- **gradient**：返回颜色 `self` 的标准渐变效果。
- **mix(with:by:in:)**：返回按 `fraction` 指定的量与`rhs` 混合的 self 版本。
- **exposureAdjust(_:)**：返回应用了曝光调整的新颜色。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/headroom(_:)
crawled: 2025-12-03T05:39:56Z
---

# headroom(_:)

**Instance Method**

Creates a new color with specified HDR content headroom.

## Declaration

```swift
func headroom(_ headroom: Double?) -> Color
```

## Parameters

- **headroom**: The headroom value to associate with the new color.

## Return Value

A new color with the specified content headroom.

## Discussion

High Dynamic Range colors (those with RGB components outside the standard [0, 1] range) should be annotated with their headroom to ensure that they are displayed correctly. Knowing content headroom allows the rendering system to automatically increase display headroom when the color is displayed and to tone map the color when the available display headroom is insufficient to render the color as intended.

For example a custom yellow color whose brightness has been increased by two exposure levels:

```swift
Color(.sRGB, red: 1.83, green: 1.47, blue: 0)
    .headroom(4)
```

note that headroom is a linear quantity, and as such any color adjustments should typically be made in a linear color space.

## Modifying a color

- **opacity(_:)**: Multiplies the opacity of the color by the given amount.
- **gradient**: Returns the standard gradient for the color `self`.
- **mix(with:by:in:)**: Returns a version of self mixed with `rhs` by the amount specified by `fraction`.
- **exposureAdjust(_:)**: Returns a new color with an exposure adjustment applied.

