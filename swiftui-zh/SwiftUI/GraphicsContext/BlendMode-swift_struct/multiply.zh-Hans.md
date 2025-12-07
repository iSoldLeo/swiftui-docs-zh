---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/multiply
抓取时间： 2025-12-03T17:20:05Z
---

# 倍增

**类型属性**

将源图像样本与背景图像样本相乘的模式。

## 声明

```swift
static var multiply: GraphicsContext.BlendMode { get }
```

## 讨论

在这种模式下绘制的颜色至少与两种样本颜色中的任何一种一样深。

## 变暗

- **darken**：通过从源图像或背景中选择较暗的样本来创建合成图像样本的模式。
- **colorBurn**：使背景图像样本变暗以反映源图像样本的模式。
- **plusDarker**：一种模式，将源图像和背景图像的颜色分量倒数相加，然后将结果反转，产生一个变暗的合成图像。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/multiply
crawled: 2025-12-03T17:20:05Z
---

# multiply

**Type Property**

A mode that multiplies the source image samples with the background image samples.

## Declaration

```swift
static var multiply: GraphicsContext.BlendMode { get }
```

## Discussion

Drawing in this mode results in colors that are at least as dark as either of the two contributing sample colors.

## Darkening

- **darken**: A mode that creates composite image samples by choosing the darker samples from either the source image or the background.
- **colorBurn**: A mode that darkens background image samples to reflect the source image samples.
- **plusDarker**: A mode that adds the inverse of the color components of the source and background images, and then inverts the result, producing a darkened composite.

