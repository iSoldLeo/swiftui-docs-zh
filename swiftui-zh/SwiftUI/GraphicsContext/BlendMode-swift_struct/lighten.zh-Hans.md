---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/lighten
抓取时间： 2025-12-03T17:20:08Z
---

# 减轻

**类型属性**

通过从源图像或背景中选择较亮的样本来创建合成图像样本的模式。

## 声明

```swift
static var lighten: GraphicsContext.BlendMode { get }
```

## 讨论

在此模式下绘制时，比背景浅的源图像样本会替换背景。否则，背景图像样本保持不变。

## 变亮

- **screen**：将源图像样本的倒数与背景图像样本的倒数相乘的模式。
- **colorDodge**：使背景图像样本变亮以反映源图像样本的模式。
- **plusLighter**：一种将源图像和背景图像的分量相加，从而得到亮化合成图像的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/lighten
crawled: 2025-12-03T17:20:08Z
---

# lighten

**Type Property**

A mode that creates composite image samples by choosing the lighter samples from either the source image or the background.

## Declaration

```swift
static var lighten: GraphicsContext.BlendMode { get }
```

## Discussion

When you draw in this mode, source image samples that are lighter than the background replace the background. Otherwise, the background image samples remain unchanged.

## Lightening

- **screen**: A mode that multiplies the inverse of the source image samples with the inverse of the background image samples.
- **colorDodge**: A mode that brightens the background image samples to reflect the source image samples.
- **plusLighter**: A mode that adds the components of the source and background images, resulting in a lightened composite.

