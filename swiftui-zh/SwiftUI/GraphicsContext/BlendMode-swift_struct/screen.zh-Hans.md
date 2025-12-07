---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/screen
抓取时间： 2025-12-03T17:20:08Z
---

# 屏幕

**类型属性**

将源图像样本的倒数与背景图像样本的倒数相乘的模式。

## 声明

```swift
static var screen: GraphicsContext.BlendMode { get }
```

## 讨论

在这种模式下绘制的颜色至少与两种样本颜色中的任何一种一样浅。

## 减淡

- **lighten**：通过从源图像或背景中选择较亮的样本来创建合成图像样本的模式。
- **colorDodge**：使背景图像样本变亮以反映源图像样本的模式。
- **plusLighter**：一种将源图像和背景图像的分量相加，从而得到亮化合成图像的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/screen
crawled: 2025-12-03T17:20:08Z
---

# screen

**Type Property**

A mode that multiplies the inverse of the source image samples with the inverse of the background image samples.

## Declaration

```swift
static var screen: GraphicsContext.BlendMode { get }
```

## Discussion

Drawing in this mode results in colors that are at least as light as either of the two contributing sample colors.

## Lightening

- **lighten**: A mode that creates composite image samples by choosing the lighter samples from either the source image or the background.
- **colorDodge**: A mode that brightens the background image samples to reflect the source image samples.
- **plusLighter**: A mode that adds the components of the source and background images, resulting in a lightened composite.

