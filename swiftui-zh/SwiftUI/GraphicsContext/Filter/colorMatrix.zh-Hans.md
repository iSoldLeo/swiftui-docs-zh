---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorMatrix(_:)
抓取时间： 2025-12-01T22:05:50Z
---

# colorMatrix(_:)

**类型方法**

返回与给定颜色矩阵相乘的滤波器。

## 声明

```swift
static func colorMatrix(_ matrix: ColorMatrix) -> GraphicsContext.Filter
```

## 参数

- **matrix**：过滤器使用的[ColorMatrix](../../ColorMatrix.zh-Hans.md) 实例。

## 返回值

使用给定矩阵变换颜色的滤波器。

## 讨论

此滤波器等同于可缩放矢量图形（SVG）规范定义的`feColorMatrix`滤波器基元。

该滤波器将输入颜色`[R, G, B, A]`乘以[ColorMatrix](../../ColorMatrix.zh-Hans.md)前四列形成的方阵，然后将第五列加入结果中，从而在每个像素上根据输入颜色`[R', G', B', A']`创建输出颜色[ColorMatrix](../../ColorMatrix.zh-Hans.md)：

```swift
R' = r1 ✕ R + r2 ✕ G + r3 ✕ B + r4 ✕ A + r5
G' = g1 ✕ R + g2 ✕ G + g3 ✕ B + g4 ✕ A + g5
B' = b1 ✕ R + b2 ✕ G + b3 ✕ B + b4 ✕ A + b5
A' = a1 ✕ R + a2 ✕ G + a3 ✕ B + a4 ✕ A + a5
```

## 操作颜色

- **saturation(_:)**：返回应用饱和度调整的滤镜。
- **colorInvert(_:)**：返回反转结果颜色的滤镜。
- **colorMultiply(_:)**：返回将每个颜色分量乘以给定颜色的匹配分量的滤波器。
- **hueRotation(_:)**：返回一个应用色调旋转调整的滤镜。
- **grayscale(_:)**：返回应用灰度调整的滤镜。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/colorMatrix(_:)
crawled: 2025-12-01T22:05:50Z
---

# colorMatrix(_:)

**Type Method**

Returns a filter that multiplies by a given color matrix.

## Declaration

```swift
static func colorMatrix(_ matrix: ColorMatrix) -> GraphicsContext.Filter
```

## Parameters

- **matrix**: A [ColorMatrix](../../ColorMatrix.zh-Hans.md) instance used by the filter.

## Return Value

A filter that transforms color using the given matrix.

## Discussion

This filter is equivalent to the `feColorMatrix` filter primitive defined by the Scalable Vector Graphics (SVG) specification.

The filter creates the output color `[R', G', B', A']` at each pixel from an input color `[R, G, B, A]` by multiplying the input color by the square matrix formed by the first four columns of the [ColorMatrix](../../ColorMatrix.zh-Hans.md), then adding the fifth column to the result:

```swift
R' = r1 ✕ R + r2 ✕ G + r3 ✕ B + r4 ✕ A + r5
G' = g1 ✕ R + g2 ✕ G + g3 ✕ B + g4 ✕ A + g5
B' = b1 ✕ R + b2 ✕ G + b3 ✕ B + b4 ✕ A + b5
A' = a1 ✕ R + a2 ✕ G + a3 ✕ B + a4 ✕ A + a5
```

## Manipulating color

- **saturation(_:)**: Returns a filter that applies a saturation adjustment.
- **colorInvert(_:)**: Returns a filter that inverts the color of their results.
- **colorMultiply(_:)**: Returns a filter that multiplies each color component by the matching component of a given color.
- **hueRotation(_:)**: Returns a filter that applies a hue rotation adjustment.
- **grayscale(_:)**: Returns a filter that applies a grayscale adjustment.

