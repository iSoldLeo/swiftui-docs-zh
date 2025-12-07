---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/softLight
抓取时间： 2025-12-03T17:20:12Z
---

# 柔光

**类型属性**

一种根据源图像样本颜色使颜色变暗或变亮的模式。

## 声明

```swift
static var softLight: GraphicsContext.BlendMode { get }
```

## 讨论

如果源图像样本颜色浅于 50% 灰色，背景会变亮，类似于减淡。如果源图像样本颜色比 50% 灰色深，背景会变暗，类似于灼烧。如果源图像样本颜色等于 50% 灰色，背景不会改变。等于纯黑或纯白的图像样本会产生更暗或更亮的区域，但不会产生纯黑或纯白的效果。整体效果类似于用漫射聚光灯照射源图像。用它可以为场景添加高光。

## 添加对比度

- **overlay**：根据背景颜色，将源图像样本与背景图像样本相乘或截屏的模式。
- **hardLight**：根据源图像样本颜色，对颜色进行倍增或筛选的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/softLight
crawled: 2025-12-03T17:20:12Z
---

# softLight

**Type Property**

A mode that either darkens or lightens colors, depending on the source image sample color.

## Declaration

```swift
static var softLight: GraphicsContext.BlendMode { get }
```

## Discussion

If the source image sample color is lighter than 50% gray, the background is lightened, similar to dodging. If the source image sample color is darker than 50% gray, the background is darkened, similar to burning. If the source image sample color is equal to 50% gray, the background is not changed. Image samples that are equal to pure black or pure white produce darker or lighter areas, but do not result in pure black or white. The overall effect is similar to what you’d achieve by shining a diffuse spotlight on the source image. Use this to add highlights to a scene.

## Adding contrast

- **overlay**: A mode that either multiplies or screens the source image samples with the background image samples, depending on the background color.
- **hardLight**: A mode that either multiplies or screens colors, depending on the source image sample color.

