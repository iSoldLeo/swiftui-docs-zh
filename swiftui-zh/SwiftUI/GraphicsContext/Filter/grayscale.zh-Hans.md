---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/grayscale(_:)
抓取时间： 2025-12-03T17:20:32Z
---

# Grayscale(_:)

**类型方法**

返回应用灰度调整的过滤器。

## 声明

```swift
static func grayscale(_ amount: Double) -> GraphicsContext.Filter
```

## 参数

- **amount**：控制效果的数值。值为 1 会使图像完全变灰。值为 0 时，效果保持不变。其他值应用线性乘数效果。

## 返回值

应用灰度调整的滤波器。

## 讨论

该滤波器等同于可缩放矢量图形（SVG）规范定义的`grayscale`滤波器基元。

## 操作颜色

- **saturation(_:)**：返回应用饱和度调整的滤镜。
- **colorInvert(_:)**：返回反转结果颜色的滤镜。
- **colorMultiply(_:)**：返回将每个颜色分量乘以给定颜色的匹配分量的滤波器。
- **hueRotation(_:)**：返回一个应用色调旋转调整的滤镜。
- **colorMatrix(_:)**：返回乘以给定颜色矩阵的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/grayscale(_:)
crawled: 2025-12-03T17:20:32Z
---

# grayscale(_:)

**Type Method**

Returns a filter that applies a grayscale adjustment.

## Declaration

```swift
static func grayscale(_ amount: Double) -> GraphicsContext.Filter
```

## Parameters

- **amount**: An amount that controls the effect. A value of one makes the image completely gray. A value of zero leaves the result unchanged. Other values apply a linear multiplier effect.

## Return Value

A filter that applies a grayscale adjustment.

## Discussion

This filter is equivalent to the `grayscale` filter primitive defined by the Scalable Vector Graphics (SVG) specification.

## Manipulating color

- **saturation(_:)**: Returns a filter that applies a saturation adjustment.
- **colorInvert(_:)**: Returns a filter that inverts the color of their results.
- **colorMultiply(_:)**: Returns a filter that multiplies each color component by the matching component of a given color.
- **hueRotation(_:)**: Returns a filter that applies a hue rotation adjustment.
- **colorMatrix(_:)**: Returns a filter that multiplies by a given color matrix.

