---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/color(_:red:green:blue:opacity:)
抓取时间：2025-12-01T22:05:01Z
---

# color(_:red:green:blue:opacity:)

**类型方法**

返回一个在给定颜色空间中填充颜色的着色实例。

## 声明

```swift
static func color(_ colorSpace: Color.RGBColorSpace = .sRGB, red: Double, green: Double, blue: Double, opacity: Double = 1) -> GraphicsContext.Shading
```

## 参数

- **colorSpace**：用于定义颜色的 RGB 颜色空间。默认值为 [sRGB](../../Color/RGBColorSpace/sRGB.zh-Hans.md)。
- **red**：颜色的红色成分。
- **green**：颜色的绿色分量。
- **blue**： 颜色的绿色分量：颜色的蓝色分量。
- **opacity**：颜色的不透明度。默认值为 `1`，表示完全不透明。

## 返回值

一个填充了颜色的阴影实例。

### 颜色

- **color(_:)**：返回一个填充了颜色的阴影实例。
- **color(_:white:opacity:)**：返回在给定颜色空间中填充单色的着色实例。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/color(_:red:green:blue:opacity:)
crawled: 2025-12-01T22:05:01Z
---

# color(_:red:green:blue:opacity:)

**Type Method**

Returns a shading instance that fills with a color in the given color space.

## Declaration

```swift
static func color(_ colorSpace: Color.RGBColorSpace = .sRGB, red: Double, green: Double, blue: Double, opacity: Double = 1) -> GraphicsContext.Shading
```

## Parameters

- **colorSpace**: The RGB color space used to define the color. The default is [sRGB](../../Color/RGBColorSpace/sRGB.zh-Hans.md).
- **red**: The red component of the color.
- **green**: The green component of the color.
- **blue**: The blue component of the color.
- **opacity**: The opacity of the color. The default is `1`, which means fully opaque.

## Return Value

A shading instance filled with a color.

## Colors

- **color(_:)**: Returns a shading instance that fills with a color.
- **color(_:white:opacity:)**: Returns a shading instance that fills with a monochrome color in the given color space.

