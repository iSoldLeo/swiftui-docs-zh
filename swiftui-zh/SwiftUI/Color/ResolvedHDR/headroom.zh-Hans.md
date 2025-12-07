---
来源： https://developer.apple.com/documentation/SwiftUI/Color/ResolvedHDR/headroom
抓取时间： 2025-12-04T11:33:58Z
---

# 净空

**实例属性**

颜色的内容余量。

## 声明

```swift
var headroom: Float? { get set }
```

## 讨论

这是标称峰值亮度（"峰值白"）与标称漫反射亮度（"参考白 "或 "漫反射白"）的比值。净空是一个线性量，即没有伽玛函数。

## 获取色彩属性

- **red**：在扩展的 sRGB 色彩空间中，颜色的红色含量。
- **green**：扩展 sRGB 色彩空间中颜色的绿度。
- **blue**：扩展 sRGB 色彩空间中颜色的蓝量。
- **linearRed**：在具有线性伽玛的扩展 sRGB 色彩空间变体中颜色的红色量。
- **linearGreen**：在具有线性伽玛的扩展 sRGB 色彩空间变体中颜色的绿度。
- **linearBlue**：在具有线性伽玛的扩展 sRGB 色彩空间变体中颜色的蓝量。
- **opacity**：颜色的不透明度，范围为 `0` 至 `1`。


---
source: https://developer.apple.com/documentation/SwiftUI/Color/ResolvedHDR/headroom
crawled: 2025-12-04T11:33:58Z
---

# headroom

**Instance Property**

The content headroom of the color.

## Declaration

```swift
var headroom: Float? { get set }
```

## Discussion

This is the ratio of nominal peak luminance (“peak white”) to nominal diffuse luminance (“reference white” or “diffuse white”). Headroom is a linear quantity, i.e. there is no gamma function applied to it.

## Getting color properties

- **red**: The amount of red in the color in the extended sRGB color space.
- **green**: The amount of green in the color in the extended sRGB color space.
- **blue**: The amount of blue in the color in the extended sRGB color space.
- **linearRed**: The amount of red in the color in the extended sRGB color space variant with linear gamma.
- **linearGreen**: The amount of green in the color in the extended sRGB color space variant with linear gamma.
- **linearBlue**: The amount of blue in the color in the extended sRGB color space variant with linear gamma.
- **opacity**: The opacity of the color, in the range `0` to `1`.

