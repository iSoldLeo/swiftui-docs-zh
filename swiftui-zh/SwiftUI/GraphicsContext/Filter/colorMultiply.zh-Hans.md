---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorMultiply(_:)
抓取时间： 2025-12-01T22:05:47Z
---

# colorMultiply(_:)

**类型方法**

返回一个过滤器，将每个颜色分量乘以给定颜色的匹配分量。

## 声明

```swift
static func colorMultiply(_ color: Color) -> GraphicsContext.Filter
```

## 参数

- **color**：滤波器进行乘法运算时使用的颜色。

## 返回值

将颜色成分相乘的滤波器。

## 操纵颜色

- **saturation(_:)**：返回应用饱和度调整的滤镜。
- **colorInvert(_:)**：返回反转结果颜色的滤镜。
- **hueRotation(_:)**：返回应用色调旋转调整的滤镜。
- **grayscale(_:)**：返回应用灰度调整的滤镜。
- **colorMatrix(_:)**：返回乘以给定颜色矩阵的滤波器。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorMultiply(_:)
crawled: 2025-12-01T22:05:47Z
---

# colorMultiply(_:)

**Type Method**

Returns a filter that multiplies each color component by the matching component of a given color.

## Declaration

```swift
static func colorMultiply(_ color: Color) -> GraphicsContext.Filter
```

## Parameters

- **color**: The color that the filter uses for the multiplication operation.

## Return Value

A filter that multiplies color components.

## Manipulating color

- **saturation(_:)**: Returns a filter that applies a saturation adjustment.
- **colorInvert(_:)**: Returns a filter that inverts the color of their results.
- **hueRotation(_:)**: Returns a filter that applies a hue rotation adjustment.
- **grayscale(_:)**: Returns a filter that applies a grayscale adjustment.
- **colorMatrix(_:)**: Returns a filter that multiplies by a given color matrix.

