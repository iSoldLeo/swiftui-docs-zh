---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/overlay
抓取时间： 2025-12-03T17:20:11Z
---

# 叠加

**类型属性**

根据背景颜色，将源图像样本与背景图像样本相乘或屏显的模式。

## 声明

```swift
static var overlay: GraphicsContext.BlendMode { get }
```

## 讨论

在此模式下绘图时，会覆盖现有的图像样本，同时保留背景的高光和阴影。背景颜色会与源图像混合，以反映背景的明暗程度。

## 添加对比度

- **softLight**：根据源图像样本颜色，使颜色变暗或变亮的模式。
- **hardLight**：根据源图像样本颜色的不同，对颜色进行倍增或屏蔽的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/overlay
crawled: 2025-12-03T17:20:11Z
---

# overlay

**Type Property**

A mode that either multiplies or screens the source image samples with the background image samples, depending on the background color.

## Declaration

```swift
static var overlay: GraphicsContext.BlendMode { get }
```

## Discussion

Drawing in this mode overlays the existing image samples while preserving the highlights and shadows of the background. The background color mixes with the source image to reflect the lightness or darkness of the background.

## Adding contrast

- **softLight**: A mode that either darkens or lightens colors, depending on the source image sample color.
- **hardLight**: A mode that either multiplies or screens colors, depending on the source image sample color.

