---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/saturation(_:)
抓取时间： 2025-12-01T22:05:46Z
---

# 饱和度(_:)

**类型 方法**

返回应用饱和度调整的过滤器。

## 声明

```swift
static func saturation(_ amount: Double) -> GraphicsContext.Filter
```

## 参数

- **amount**：饱和度调整量。值为 0 时会使每个像素完全失饱和，而值为 1 时则不会有任何变化。您可以使用大于 1 的值。

## 返回值

应用饱和度调整的滤镜。

## 讨论

该滤波器等同于可缩放矢量图形（SVG）规范定义的`saturate`滤波器基元。

## 操作颜色

- **colorInvert(_:)**：返回反转结果颜色的过滤器。
- **colorMultiply(_:)**：返回将每个颜色分量乘以给定颜色的匹配分量的滤波器。
- **hueRotation(_:)**：返回一个应用色调旋转调整的滤镜。
- **grayscale(_:)**：返回应用灰度调整的滤镜。
- **colorMatrix(_:)**：返回乘以给定颜色矩阵的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/saturation(_:)
crawled: 2025-12-01T22:05:46Z
---

# saturation(_:)

**Type Method**

Returns a filter that applies a saturation adjustment.

## Declaration

```swift
static func saturation(_ amount: Double) -> GraphicsContext.Filter
```

## Parameters

- **amount**: The amount of the saturation adjustment. A value of zero to completely desaturates each pixel, while a value of one makes no change. You can use values greater than one.

## Return Value

A filter that applies a saturation adjustment.

## Discussion

This filter is equivalent to the `saturate` filter primitive defined by the Scalable Vector Graphics (SVG) specification.

## Manipulating color

- **colorInvert(_:)**: Returns a filter that inverts the color of their results.
- **colorMultiply(_:)**: Returns a filter that multiplies each color component by the matching component of a given color.
- **hueRotation(_:)**: Returns a filter that applies a hue rotation adjustment.
- **grayscale(_:)**: Returns a filter that applies a grayscale adjustment.
- **colorMatrix(_:)**: Returns a filter that multiplies by a given color matrix.

