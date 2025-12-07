---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/colorBurn
抓取时间： 2025-12-03T17:20:06Z
---

# colorBurn

**类型属性**

使背景图像样本变暗以反映源图像样本的模式。

## 声明

```swift
static var colorBurn: GraphicsContext.BlendMode { get }
```

## 讨论

指定白色的源图像样本值不会产生变化。

## 变暗

- **darken**：通过从源图像或背景中选择较暗的样本来创建复合图像样本的模式。
- **multiply**：将源图像样本与背景图像样本相乘的模式。
- **plusDarker**：将源图像和背景图像的颜色分量进行倒相加，然后将结果反转，产生一个变暗的合成图像的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/colorBurn
crawled: 2025-12-03T17:20:06Z
---

# colorBurn

**Type Property**

A mode that darkens background image samples to reflect the source image samples.

## Declaration

```swift
static var colorBurn: GraphicsContext.BlendMode { get }
```

## Discussion

Source image sample values that specify white do not produce a change.

## Darkening

- **darken**: A mode that creates composite image samples by choosing the darker samples from either the source image or the background.
- **multiply**: A mode that multiplies the source image samples with the background image samples.
- **plusDarker**: A mode that adds the inverse of the color components of the source and background images, and then inverts the result, producing a darkened composite.

