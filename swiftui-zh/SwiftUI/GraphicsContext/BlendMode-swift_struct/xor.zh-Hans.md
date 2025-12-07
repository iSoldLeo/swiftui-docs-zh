---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/xor
抓取时间： 2025-12-03T17:20:27Z
---

# xor

**类型属性**

用于清除源图像和背景图像都不透明的像素的模式。

## 声明

```swift
static var xor: GraphicsContext.BlendMode { get }
```

## 讨论

该模式实现了 `R = S*(1 - Da) + D*(1 - Sa)` 等式，其中

- `R`为合成图像。
- `S`是源图像。
- `D`为背景。
- `Sa`是源图像的 alpha 值。
- `Da`是源背景的 alpha 值。

这种 XOR 模式名义上与经典的位图 XOR 操作有关，但 SwiftUI 不支持这种操作。

## 访问波特-达夫模式

- **clear**：清除源图像覆盖的任何像素的模式。
- **copy**：用源图像样本替换背景图像样本的模式。
- **sourceIn**：将源图像（包括其透明度）绘制到背景不透明部分的模式。
- **sourceOut**：用于将源图像绘制到背景的透明部分上，同时擦除背景的模式。
- **sourceAtop**：用于将源图像的不透明部分绘制到背景的不透明部分上的模式。
- **destinationOver**：用于在背景下绘制源图像的模式。
- **destinationIn**：用于擦除未被不透明源像素覆盖的背景的模式。
- **destinationOut**：用于擦除被不透明源像素覆盖的任何背景的模式。
- **destinationAtop**：用于在背景下绘制源图像，同时擦除源图像中不透明像素未匹配的任何背景的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/xor
crawled: 2025-12-03T17:20:27Z
---

# xor

**Type Property**

A mode that you use to clear pixels where both the source and background images are opaque.

## Declaration

```swift
static var xor: GraphicsContext.BlendMode { get }
```

## Discussion

This mode implements the equation `R = S*(1 - Da) + D*(1 - Sa)` where

- `R` is the composite image.
- `S` is the source image.
- `D` is the background.
- `Sa` is the source image’s alpha value.
- `Da` is the source background’s alpha value.

This XOR mode is only nominally related to the classical bitmap XOR operation, which SwiftUI doesn’t support.

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

