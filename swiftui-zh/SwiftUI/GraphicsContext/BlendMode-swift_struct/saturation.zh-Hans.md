---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/saturation
抓取时间： 2025-12-03T17:20:16Z
---

# 饱和度

**类型属性**

一种使用背景亮度和色调值以及源图像饱和度的模式。

## 声明

```swift
static var saturation: GraphicsContext.BlendMode { get }
```

## 讨论

背景中没有饱和度的区域（即纯灰色区域）不会产生变化。

## 混合颜色成分

- **hue**：使用背景的亮度和饱和度值以及源图像的色调的模式。
- **color**：使用背景亮度值与源图像色调和饱和度值的模式。
- **luminosity**：使用背景的色调和饱和度以及源图像的亮度的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/saturation
crawled: 2025-12-03T17:20:16Z
---

# saturation

**Type Property**

A mode that uses the luminance and hue values of the background with the saturation of the source image.

## Declaration

```swift
static var saturation: GraphicsContext.BlendMode { get }
```

## Discussion

Areas of the background that have no saturation — namely, pure gray areas — don’t produce a change.

## Mixing color components

- **hue**: A mode that uses the luminance and saturation values of the background with the hue of the source image.
- **color**: A mode that uses the luminance values of the background with the hue and saturation values of the source image.
- **luminosity**: A mode that uses the hue and saturation of the background with the luminance of the source image.

