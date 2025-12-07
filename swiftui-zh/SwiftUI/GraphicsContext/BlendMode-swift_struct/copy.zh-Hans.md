---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/copy
抓取时间： 2025-12-03T17:20:20Z
---

# 复制

**类型属性**

用源图像样本替换背景图像样本的模式。

## 声明

```swift
static var copy: GraphicsContext.BlendMode { get }
```

## 讨论

与 [normal](normal.zh-Hans.md) 模式不同，源图像会完全取代背景，因此即使源图像中的透明像素也会取代背景中的不透明像素，而不会让背景显示出来。

这种模式实现了 `R = S` 等式，其中

- `R` 是合成图像。
- `S`为源图像。

## 访问波特-达夫模式

- **clear**：清除源图像覆盖的任何像素的模式。
- **sourceIn**：用于将源图像（包括其透明度）绘制到背景的不透明部分的模式。
- **sourceOut**：用于将源图像绘制到背景的透明部分，同时擦除背景的模式。
- **sourceAtop**：用于将源图像的不透明部分绘制到背景的不透明部分上的模式。
- **destinationOver**：用于在背景下绘制源图像的模式。
- **destinationIn**：用于擦除未被不透明源像素覆盖的背景的模式。
- **destinationOut**：用于擦除被不透明源像素覆盖的任何背景的模式。
- **destinationAtop**：用于在背景下绘制源图像，同时擦除源图像中不透明像素未匹配的任何背景的模式。
- **xor**：用于清除源图像和背景图像都不透明的像素的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/copy
crawled: 2025-12-03T17:20:20Z
---

# copy

**Type Property**

A mode that replaces background image samples with source image samples.

## Declaration

```swift
static var copy: GraphicsContext.BlendMode { get }
```

## Discussion

Unlike the [normal](normal.zh-Hans.md) mode, the source image completely replaces the background, so that even transparent pixels in the source image replace opaque pixels in the background, rather than letting the background show through.

This mode implements the equation `R = S` where

- `R` is the composite image.
- `S` is the source image.

## Accessing porter-duff modes

- **clear**: A mode that clears any pixels that the source image overwrites.
- **sourceIn**: A mode that you use to paint the source image, including its transparency, onto the opaque parts of the background.
- **sourceOut**: A mode that you use to paint the source image onto the transparent parts of the background, while erasing the background.
- **sourceAtop**: A mode that you use to paint the opaque parts of the source image onto the opaque parts of the background.
- **destinationOver**: A mode that you use to paint the source image under the background.
- **destinationIn**: A mode that you use to erase any of the background that isn’t covered by opaque source pixels.
- **destinationOut**: A mode that you use to erase any of the background that is covered by opaque source pixels.
- **destinationAtop**: A mode that you use to paint the source image under the background, while erasing any of the background not matched by opaque pixels from the source image.
- **xor**: A mode that you use to clear pixels where both the source and background images are opaque.

