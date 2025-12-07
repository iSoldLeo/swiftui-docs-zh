---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct
抓取时间： 2025-12-02T20:58:21Z
---

# GraphicsContext.BlendMode

**Structure**

图形上下文将新内容与背景内容相结合的方式。

## 声明

```swift
@frozen struct BlendMode
```

## 概览

使用这些值之一来设置[blendMode-swift.property](blendMode-swift_property.zh-Hans.md) 属性的[GraphicsContext](../GraphicsContext.zh-Hans.md)。您设置的值会影响您绘制的内容如何替换或结合您之前绘制到上下文中的内容。

## 获取默认值

- **normal**：在背景图像样本上绘制源图像样本的模式。

## 变暗

- **darken**：通过从源图像或背景图像中选择较暗的样本来创建合成图像样本的模式。
- **multiply**：将源图像样本与背景图像样本相乘的模式。
- **colorBurn**：使背景图像采样变暗以反映源图像采样的模式。
- **plusDarker**：一种模式，将源图像和背景图像的颜色分量相加，然后将结果反转，产生一个变暗的合成图像。

## 变亮

- **lighten**：通过从源图像或背景中选择较亮的样本来创建合成图像样本的模式。
- **screen**：将源图像样本的倒数与背景图像样本的倒数相乘的模式。
- **colorDodge**：使背景图像样本变亮以反映源图像样本的模式。
- **plusLighter**：一种将源图像和背景图像的分量相加，从而得到减亮合成图像的模式。

## 增加对比度

- **overlay**：根据背景颜色，将源图像样本与背景图像样本相乘或截屏的模式。
- **softLight**：根据源图像样本的颜色，使颜色变暗或变亮的模式。
- **hardLight**：根据源图像样本颜色的不同，将颜色放大或缩小的模式。

## 反色

- **difference**：从源图像样本颜色或背景图像样本颜色中减去较亮的颜色的模式。
- **exclusion**：产生类似于差值混合模式的效果，但对比度较低的模式。

## 混合颜色成分

- **hue**：使用背景的亮度和饱和度值以及源图像的色调的模式。
- **saturation**：使用背景的亮度和色调值以及源图像的饱和度的模式。
- **color**：使用背景亮度值与源图像的色调值和饱和度值的模式。
- **luminosity**：使用背景的色调和饱和度以及源图像的亮度的模式。

## 访问波特杜夫模式

- **clear**：清除源图像覆盖的任何像素的模式。
- **copy**：用源图像样本替换背景图像样本的模式。
- **sourceIn**：将源图像（包括其透明度）绘制到背景不透明部分的模式。
- **sourceOut**：用于将源图像绘制到背景的透明部分，同时擦除背景的模式。
- **sourceAtop**：用于将源图像的不透明部分绘制到背景的不透明部分上的模式。
- **destinationOver**：用于在背景下绘制源图像的模式。
- **destinationIn**：用于擦除未被不透明源像素覆盖的背景的模式。
- **destinationOut**：用于擦除被不透明源像素覆盖的任何背景的模式。
- **destinationAtop**：用于在背景下绘制源图像的模式，同时擦除与源图像中不透明像素不匹配的任何背景。
- **xor**：用于清除源图像和背景图像都不透明的像素的模式。

### 设置不透明度和混合模式

- **opacity**：上下文中绘图操作的不透明度。
- **blendMode**：上下文中绘图操作使用的混合模式。

## 符合

- 比特可复制
- 可复制
- 等价
- 可原始呈现
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct
crawled: 2025-12-02T20:58:21Z
---

# GraphicsContext.BlendMode

**Structure**

The ways that a graphics context combines new content with background content.

## Declaration

```swift
@frozen struct BlendMode
```

## Overview

Use one of these values to set the [blendMode-swift.property](blendMode-swift_property.zh-Hans.md) property of a [GraphicsContext](../GraphicsContext.zh-Hans.md). The value that you set affects how content that you draw replaces or combines with content that you previously drew into the context.

## Getting the default

- **normal**: A mode that paints source image samples over the background image samples.

## Darkening

- **darken**: A mode that creates composite image samples by choosing the darker samples from either the source image or the background.
- **multiply**: A mode that multiplies the source image samples with the background image samples.
- **colorBurn**: A mode that darkens background image samples to reflect the source image samples.
- **plusDarker**: A mode that adds the inverse of the color components of the source and background images, and then inverts the result, producing a darkened composite.

## Lightening

- **lighten**: A mode that creates composite image samples by choosing the lighter samples from either the source image or the background.
- **screen**: A mode that multiplies the inverse of the source image samples with the inverse of the background image samples.
- **colorDodge**: A mode that brightens the background image samples to reflect the source image samples.
- **plusLighter**: A mode that adds the components of the source and background images, resulting in a lightened composite.

## Adding contrast

- **overlay**: A mode that either multiplies or screens the source image samples with the background image samples, depending on the background color.
- **softLight**: A mode that either darkens or lightens colors, depending on the source image sample color.
- **hardLight**: A mode that either multiplies or screens colors, depending on the source image sample color.

## Inverting

- **difference**: A mode that subtracts the brighter of the source image sample color or the background image sample color from the other.
- **exclusion**: A mode that produces an effect similar to that produced by the difference blend mode, but with lower contrast.

## Mixing color components

- **hue**: A mode that uses the luminance and saturation values of the background with the hue of the source image.
- **saturation**: A mode that uses the luminance and hue values of the background with the saturation of the source image.
- **color**: A mode that uses the luminance values of the background with the hue and saturation values of the source image.
- **luminosity**: A mode that uses the hue and saturation of the background with the luminance of the source image.

## Accessing porter-duff modes

- **clear**: A mode that clears any pixels that the source image overwrites.
- **copy**: A mode that replaces background image samples with source image samples.
- **sourceIn**: A mode that you use to paint the source image, including its transparency, onto the opaque parts of the background.
- **sourceOut**: A mode that you use to paint the source image onto the transparent parts of the background, while erasing the background.
- **sourceAtop**: A mode that you use to paint the opaque parts of the source image onto the opaque parts of the background.
- **destinationOver**: A mode that you use to paint the source image under the background.
- **destinationIn**: A mode that you use to erase any of the background that isn’t covered by opaque source pixels.
- **destinationOut**: A mode that you use to erase any of the background that is covered by opaque source pixels.
- **destinationAtop**: A mode that you use to paint the source image under the background, while erasing any of the background not matched by opaque pixels from the source image.
- **xor**: A mode that you use to clear pixels where both the source and background images are opaque.

## Setting opacity and the blend mode

- **opacity**: The opacity of drawing operations in the context.
- **blendMode**: The blend mode used by drawing operations in the context.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- RawRepresentable
- Sendable
- SendableMetatype

