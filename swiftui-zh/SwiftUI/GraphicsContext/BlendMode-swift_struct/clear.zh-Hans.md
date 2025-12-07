---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/clear
抓取时间： 2025-12-03T17:20:19Z
---

# 清除

**类型属性**

清除源图像覆盖的任何像素的模式。

## 声明

```swift
static var clear: GraphicsContext.BlendMode { get }
```

## 讨论

使用这种模式，可以像使用橡皮擦一样使用源图像。

该模式实现了 `R = 0` 等式，其中 `R` 是合成图像。

## 访问波特杜夫模式

- **copy**：用源图像样本替换背景图像样本的模式。
- **sourceIn**：将源图像（包括其透明度）绘制到背景不透明部分的模式。
- **sourceOut**：用于将源图像绘制到背景的透明部分，同时擦除背景的模式。
- **sourceAtop**：用于将源图像的不透明部分绘制到背景的不透明部分上的模式。
- **destinationOver**：用于在背景下绘制源图像的模式。
- **destinationIn**：用于擦除未被不透明源像素覆盖的背景的模式。
- **destinationOut**：用于擦除被不透明源像素覆盖的任何背景的模式。
- **destinationAtop**：用于在背景下绘制源图像的模式，同时擦除与源图像中不透明像素不匹配的任何背景。
- **xor**：用于清除源图像和背景图像都不透明的像素的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/clear
crawled: 2025-12-03T17:20:19Z
---

# clear

**Type Property**

A mode that clears any pixels that the source image overwrites.

## Declaration

```swift
static var clear: GraphicsContext.BlendMode { get }
```

## Discussion

With this mode, you can use the source image like an eraser.

This mode implements the equation `R = 0` where `R` is the composite image.

## Accessing porter-duff modes

- **copy**: A mode that replaces background image samples with source image samples.
- **sourceIn**: A mode that you use to paint the source image, including its transparency, onto the opaque parts of the background.
- **sourceOut**: A mode that you use to paint the source image onto the transparent parts of the background, while erasing the background.
- **sourceAtop**: A mode that you use to paint the opaque parts of the source image onto the opaque parts of the background.
- **destinationOver**: A mode that you use to paint the source image under the background.
- **destinationIn**: A mode that you use to erase any of the background that isn’t covered by opaque source pixels.
- **destinationOut**: A mode that you use to erase any of the background that is covered by opaque source pixels.
- **destinationAtop**: A mode that you use to paint the source image under the background, while erasing any of the background not matched by opaque pixels from the source image.
- **xor**: A mode that you use to clear pixels where both the source and background images are opaque.

