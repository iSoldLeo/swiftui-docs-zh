---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/colorDodge
抓取时间： 2025-12-03T17:20:10Z
---

# colorDodge

**类型属性**

使背景图像样本变亮以反映源图像样本的模式。

## 声明

```swift
static var colorDodge: GraphicsContext.BlendMode { get }
```

## 讨论

指定为黑色的源图像样本值不会产生变化。

## 变亮

- **lighten**：通过从源图像或背景中选择较亮的样本来创建合成图像样本的模式。
- **screen**：将源图像样本的倒数与背景图像样本的倒数相乘的模式。
- **plusLighter**：将源图像和背景图像的分量相加，得到减淡合成图像的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/colorDodge
crawled: 2025-12-03T17:20:10Z
---

# colorDodge

**Type Property**

A mode that brightens the background image samples to reflect the source image samples.

## Declaration

```swift
static var colorDodge: GraphicsContext.BlendMode { get }
```

## Discussion

Source image sample values that specify black do not produce a change.

## Lightening

- **lighten**: A mode that creates composite image samples by choosing the lighter samples from either the source image or the background.
- **screen**: A mode that multiplies the inverse of the source image samples with the inverse of the background image samples.
- **plusLighter**: A mode that adds the components of the source and background images, resulting in a lightened composite.

