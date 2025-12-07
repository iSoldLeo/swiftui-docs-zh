---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorInvert(_:)
抓取时间： 2025-12-01T22:05:47Z
---

# colorInvert(_:)

**类型方法**

返回反转结果颜色的过滤器。

## 声明

```swift
static func colorInvert(_ amount: Double = 1) -> GraphicsContext.Filter
```

## 参数

- **amount**：反转量。值为 1 时，结果完全反转；值为 0 时，结果保持不变。其他值应用线性乘数效果。

## 返回值

应用颜色反转的滤波器。

## 讨论

该滤波器等同于可缩放矢量图形（SVG）规范定义的`invert`滤波器基元。

## 操作颜色

- **saturation(_:)**：返回应用饱和度调整的滤镜。
- **colorMultiply(_:)**：返回将每个颜色分量乘以给定颜色的匹配分量的滤波器。
- **hueRotation(_:)**：返回一个应用色调旋转调整的滤镜。
- **grayscale(_:)**：返回应用灰度调整的滤镜。
- **colorMatrix(_:)**：返回乘以给定颜色矩阵的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorInvert(_:)
crawled: 2025-12-01T22:05:47Z
---

# colorInvert(_:)

**Type Method**

Returns a filter that inverts the color of their results.

## Declaration

```swift
static func colorInvert(_ amount: Double = 1) -> GraphicsContext.Filter
```

## Parameters

- **amount**: The inversion amount. A value of one results in total inversion, while a value of zero leaves the result unchanged. Other values apply a linear multiplier effect.

## Return Value

A filter that applies a color inversion.

## Discussion

This filter is equivalent to the `invert` filter primitive defined by the Scalable Vector Graphics (SVG) specification.

## Manipulating color

- **saturation(_:)**: Returns a filter that applies a saturation adjustment.
- **colorMultiply(_:)**: Returns a filter that multiplies each color component by the matching component of a given color.
- **hueRotation(_:)**: Returns a filter that applies a hue rotation adjustment.
- **grayscale(_:)**: Returns a filter that applies a grayscale adjustment.
- **colorMatrix(_:)**: Returns a filter that multiplies by a given color matrix.

