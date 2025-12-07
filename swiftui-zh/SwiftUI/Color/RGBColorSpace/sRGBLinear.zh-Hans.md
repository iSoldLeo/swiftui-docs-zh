---
来源： https://developer.apple.com/documentation/SwiftUI/Color/RGBColorSpace/sRGBLinear
抓取时间： 2025-12-04T11:33:51Z
---

# Color.RGBColorSpace.sRGBLinear

**Case**

具有线性传递函数的扩展 sRGB 色彩空间。

## 声明

```swift
case sRGBLinear
```

## 讨论

该色彩空间与[sRGB](sRGB.zh-Hans.md) 具有相同的色彩度量，但使用的是线性传递函数。

标准 sRGB 色彩空间将颜色的红、绿、蓝分量限制在 `0` 至 `1` 的范围内，但 SwiftUI 颜色使用的是扩展 sRGB 色彩空间，因此可以使用该范围之外的分量值。

## 获取色彩空间

- **Color.RGBColorSpace.sRGB**：扩展的红、绿、蓝（sRGB）色彩空间。
- **Color.RGBColorSpace.displayP3**：显示 P3 色彩空间。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/RGBColorSpace/sRGBLinear
crawled: 2025-12-04T11:33:51Z
---

# Color.RGBColorSpace.sRGBLinear

**Case**

The extended sRGB color space with a linear transfer function.

## Declaration

```swift
case sRGBLinear
```

## Discussion

This color space has the same colorimetry as [sRGB](sRGB.zh-Hans.md), but uses a linear transfer function.

Standard sRGB color spaces clamp the red, green, and blue components of a color to a range of `0` to `1`, but SwiftUI colors use an extended sRGB color space, so you can use component values outside that range.

## Getting color spaces

- **Color.RGBColorSpace.sRGB**: The extended red, green, blue (sRGB) color space.
- **Color.RGBColorSpace.displayP3**: The Display P3 color space.

