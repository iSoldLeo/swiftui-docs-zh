---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/plusDarker
抓取时间： 2025-12-03T17:20:07Z
---

# plusDarker

**类型属性**

一种模式，将源图像和背景图像的颜色分量相加，然后反转结果，产生一个变暗的合成图像。

### 声明

```swift
static var plusDarker: GraphicsContext.BlendMode { get }
```

## 讨论

该模式实现了 `R = MAX(0, 1 - ((1 - D) + (1 - S)))` 等式，其中

- `R` 是合成图像。
- `S`是源图像。
- `D`为背景。

## 变暗

- **darken**：通过从源图像或背景中选择较暗的样本来创建合成图像样本的模式。
- **multiply**：将源图像样本与背景图像样本相乘的模式。
- **colorBurn**：使背景图像采样变暗以反映源图像采样的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/plusDarker
crawled: 2025-12-03T17:20:07Z
---

# plusDarker

**Type Property**

A mode that adds the inverse of the color components of the source and background images, and then inverts the result, producing a darkened composite.

## Declaration

```swift
static var plusDarker: GraphicsContext.BlendMode { get }
```

## Discussion

This mode implements the equation `R = MAX(0, 1 - ((1 - D) + (1 - S)))` where

- `R` is the composite image.
- `S` is the source image.
- `D` is the background.

## Darkening

- **darken**: A mode that creates composite image samples by choosing the darker samples from either the source image or the background.
- **multiply**: A mode that multiplies the source image samples with the background image samples.
- **colorBurn**: A mode that darkens background image samples to reflect the source image samples.

