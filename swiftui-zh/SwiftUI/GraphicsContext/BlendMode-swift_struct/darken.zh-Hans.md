---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/darken
抓取时间： 2025-12-03T17:20:04Z
---

# 变暗

**类型属性**

一种模式，通过从源图像或背景中选择较暗的样本来创建复合图像样本。

## 声明

```swift
static var darken: GraphicsContext.BlendMode { get }
```

## 讨论

在此模式下绘制时，比背景颜色深的源图像样本会取代背景。否则，背景图像样本保持不变。

## 变暗

- **multiply**：将源图像样本与背景图像样本相乘的模式。
- **colorBurn**：使背景图像采样变暗以反映源图像采样的模式。
- **plusDarker**：一种模式，将源图像和背景图像的颜色分量倒数相加，然后将结果反转，产生一个变暗的合成图像。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/darken
crawled: 2025-12-03T17:20:04Z
---

# darken

**Type Property**

A mode that creates composite image samples by choosing the darker samples from either the source image or the background.

## Declaration

```swift
static var darken: GraphicsContext.BlendMode { get }
```

## Discussion

When you draw in this mode, source image samples that are darker than the background replace the background. Otherwise, the background image samples remain unchanged.

## Darkening

- **multiply**: A mode that multiplies the source image samples with the background image samples.
- **colorBurn**: A mode that darkens background image samples to reflect the source image samples.
- **plusDarker**: A mode that adds the inverse of the color components of the source and background images, and then inverts the result, producing a darkened composite.

