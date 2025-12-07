---
来源： https://developer.apple.com/documentation/SwiftUI/Color/RGBColorSpace/sRGB
抓取时间： 2025-12-04T11:33:50Z
---

# Color.RGBColorSpace.sRGB

**Case**

扩展的红、绿、蓝（sRGB）色彩空间。

## 声明

```swift
case sRGB
```

## 讨论

有关 sRGB 色度和非线性变换函数的信息，请参阅 IEC 61966-2-1 规范。

标准 sRGB 色彩空间将颜色的红、绿、蓝分量限制在`0`至`1`的范围内，但 SwiftUI 颜色使用的是扩展 sRGB 色彩空间，因此可以使用该范围之外的分量值。

## 获取色彩空间

- **Color.RGBColorSpace.sRGBLinear**：具有线性传递函数的扩展 sRGB 色彩空间。
- **Color.RGBColorSpace.displayP3**：显示 P3 色彩空间。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/RGBColorSpace/sRGB
crawled: 2025-12-04T11:33:50Z
---

# Color.RGBColorSpace.sRGB

**Case**

The extended red, green, blue (sRGB) color space.

## Declaration

```swift
case sRGB
```

## Discussion

For information about the sRGB colorimetry and nonlinear transform function, see the IEC 61966-2-1 specification.

Standard sRGB color spaces clamp the red, green, and blue components of a color to a range of `0` to `1`, but SwiftUI colors use an extended sRGB color space, so you can use component values outside that range.

## Getting color spaces

- **Color.RGBColorSpace.sRGBLinear**: The extended sRGB color space with a linear transfer function.
- **Color.RGBColorSpace.displayP3**: The Display P3 color space.

