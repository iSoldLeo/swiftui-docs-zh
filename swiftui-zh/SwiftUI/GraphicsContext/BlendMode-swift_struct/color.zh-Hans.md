---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/color
抓取时间： 2025-12-03T17:20:17Z
---

# 颜色

**类型属性**

使用背景亮度值与源图像色调和饱和度值的模式。

## 声明

```swift
static var color: GraphicsContext.BlendMode { get }
```

## 讨论

该模式保留图像的灰度级。您可以使用此模式为单色图像着色或为彩色图像着色。

## 混合色彩成分

- **hue**：使用背景的亮度和饱和度值以及源图像的色调的模式。
- **saturation**：使用背景的亮度和色调值以及源图像的饱和度的模式。
- **luminosity**：使用背景的色调和饱和度以及源图像的亮度的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/color
crawled: 2025-12-03T17:20:17Z
---

# color

**Type Property**

A mode that uses the luminance values of the background with the hue and saturation values of the source image.

## Declaration

```swift
static var color: GraphicsContext.BlendMode { get }
```

## Discussion

This mode preserves the gray levels in the image. You can use this mode to color monochrome images or to tint color images.

## Mixing color components

- **hue**: A mode that uses the luminance and saturation values of the background with the hue of the source image.
- **saturation**: A mode that uses the luminance and hue values of the background with the saturation of the source image.
- **luminosity**: A mode that uses the hue and saturation of the background with the luminance of the source image.

