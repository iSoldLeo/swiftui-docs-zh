---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/plusLighter
抓取时间： 2025-12-03T17:20:10Z
---

# plusLighter

**类型属性**

一种模式，用于添加源图像和背景图像的分量，从而产生一个减淡的合成图像。

## 声明

```swift
static var plusLighter: GraphicsContext.BlendMode { get }
```

## 讨论

该模式实现了 `R = MIN(1, S + D)` 等式，其中

- `R` 是合成图像。
- `S`是源图像。
- `D`为背景。

## Lightening

- **lighten**：通过从源图像或背景中选择较亮的样本来创建合成图像样本的模式。
- **screen**：将源图像样本的倒数与背景图像样本的倒数相乘的模式。
- **colorDodge**：使背景图像样本变亮以反映源图像样本的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/plusLighter
crawled: 2025-12-03T17:20:10Z
---

# plusLighter

**Type Property**

A mode that adds the components of the source and background images, resulting in a lightened composite.

## Declaration

```swift
static var plusLighter: GraphicsContext.BlendMode { get }
```

## Discussion

This mode implements the equation `R = MIN(1, S + D)` where

- `R` is the composite image.
- `S` is the source image.
- `D` is the background.

## Lightening

- **lighten**: A mode that creates composite image samples by choosing the lighter samples from either the source image or the background.
- **screen**: A mode that multiplies the inverse of the source image samples with the inverse of the background image samples.
- **colorDodge**: A mode that brightens the background image samples to reflect the source image samples.

