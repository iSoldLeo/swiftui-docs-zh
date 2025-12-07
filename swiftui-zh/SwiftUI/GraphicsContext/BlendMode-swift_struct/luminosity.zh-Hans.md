---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/luminosity
抓取时间： 2025-12-03T17:20:18Z
---

# 亮度

**类型属性**

使用背景的色调和饱和度以及源图像的亮度的模式。

## 声明

```swift
static var luminosity: GraphicsContext.BlendMode { get }
```

## 讨论

该模式产生的效果与 [color](color.zh-Hans.md) 模式产生的效果相反。

## 混合色彩成分

- **hue**：使用背景的亮度和饱和度值以及源图像的色调的模式。
- **saturation**：使用背景的亮度和色调值以及源图像的饱和度的模式。
- **color**：使用背景亮度值与源图像的色调值和饱和度值的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/luminosity
crawled: 2025-12-03T17:20:18Z
---

# luminosity

**Type Property**

A mode that uses the hue and saturation of the background with the luminance of the source image.

## Declaration

```swift
static var luminosity: GraphicsContext.BlendMode { get }
```

## Discussion

This mode creates an effect that is inverse to the effect created by the [color](color.zh-Hans.md) mode.

## Mixing color components

- **hue**: A mode that uses the luminance and saturation values of the background with the hue of the source image.
- **saturation**: A mode that uses the luminance and hue values of the background with the saturation of the source image.
- **color**: A mode that uses the luminance values of the background with the hue and saturation values of the source image.

