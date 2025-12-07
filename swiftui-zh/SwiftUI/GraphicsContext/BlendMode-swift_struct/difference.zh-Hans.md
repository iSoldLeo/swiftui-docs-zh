---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/difference
抓取时间： 2025-12-03T17:20:14Z
---

# 差异

**类型属性**

从源图像样本颜色或背景图像样本颜色中减去较亮颜色的模式。

## 声明

```swift
static var difference: GraphicsContext.BlendMode { get }
```

## 讨论

黑色的源图像样本值不会产生任何变化；白色则会反转背景颜色值。

## 倒置

- **exclusion**：与差值混合模式产生的效果类似，但对比度较低。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlendMode-swift.struct/difference
crawled: 2025-12-03T17:20:14Z
---

# difference

**Type Property**

A mode that subtracts the brighter of the source image sample color or the background image sample color from the other.

## Declaration

```swift
static var difference: GraphicsContext.BlendMode { get }
```

## Discussion

Source image sample values that are black produce no change; white inverts the background color values.

## Inverting

- **exclusion**: A mode that produces an effect similar to that produced by the difference blend mode, but with lower contrast.

