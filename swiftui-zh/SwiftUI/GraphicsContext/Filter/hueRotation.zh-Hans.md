---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/hueRotation(_:)
抓取时间： 2025-12-03T17:20:31Z
---

# hueRotation(_:)

**类型方法**

返回应用色调旋转调整的滤镜。

## 声明

```swift
static func hueRotation(_ angle: Angle) -> GraphicsContext.Filter
```

## 参数

- **angle**：旋转每个像素色调值的量。

## 返回值

应用色调旋转调整的滤波器。

## 讨论

该滤波器等同于可缩放矢量图形（SVG）规范中定义的`hue-rotate`滤波器基元。

## 操作颜色

- **saturation(_:)**：返回应用饱和度调整的滤镜。
- **colorInvert(_:)**：返回反转结果颜色的滤镜。
- **colorMultiply(_:)**：返回将每个颜色分量乘以给定颜色的匹配分量的滤波器。
- **grayscale(_:)**：返回应用灰度调整的滤波器。
- **colorMatrix(_:)**：返回乘以给定颜色矩阵的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/hueRotation(_:)
crawled: 2025-12-03T17:20:31Z
---

# hueRotation(_:)

**Type Method**

Returns a filter that applies a hue rotation adjustment.

## Declaration

```swift
static func hueRotation(_ angle: Angle) -> GraphicsContext.Filter
```

## Parameters

- **angle**: The amount by which to rotate the hue value of each pixel.

## Return Value

A filter that applies a hue rotation adjustment.

## Discussion

This filter is equivalent to the `hue-rotate` filter primitive defined by the Scalable Vector Graphics (SVG) specification.

## Manipulating color

- **saturation(_:)**: Returns a filter that applies a saturation adjustment.
- **colorInvert(_:)**: Returns a filter that inverts the color of their results.
- **colorMultiply(_:)**: Returns a filter that multiplies each color component by the matching component of a given color.
- **grayscale(_:)**: Returns a filter that applies a grayscale adjustment.
- **colorMatrix(_:)**: Returns a filter that multiplies by a given color matrix.

