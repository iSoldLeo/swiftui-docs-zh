---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/exclusion
抓取时间： 2025-12-03T17:20:15Z
---

# 排除

**类型属性**

一种产生与差异混合模式类似效果的模式，但对比度较低。

## 声明

```swift
static var exclusion: GraphicsContext.BlendMode { get }
```

## 讨论

黑色的源图像样本值不会产生变化；白色会反转背景颜色值。

## 倒置

- **difference**：从源图像样本颜色或背景图像样本颜色中减去较亮者的模式。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/exclusion
crawled: 2025-12-03T17:20:15Z
---

# exclusion

**Type Property**

A mode that produces an effect similar to that produced by the difference blend mode, but with lower contrast.

## Declaration

```swift
static var exclusion: GraphicsContext.BlendMode { get }
```

## Discussion

Source image sample values that are black don’t produce a change; white inverts the background color values.

## Inverting

- **difference**: A mode that subtracts the brighter of the source image sample color or the background image sample color from the other.

