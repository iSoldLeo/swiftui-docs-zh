---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/GradientOptions/mirror
抓取时间： 2025-12-03T17:19:54Z
---

# 镜像

**类型属性**

在标称范围外重复渐变的选项，反映每一个其他实例。

## 声明

```swift
static var mirror: GraphicsContext.GradientOptions { get }
```

## 讨论

使用此选项可使渐变效果在超出起点和终点范围的区域重复其图案。这些重复会交替颠倒起点和终点，产生类似 `0 -> 1`、`1 -> 0`、`0 -> 1` 这样的图案。

如果没有该选项或[repeat](repeat.zh-Hans.md)，梯度会在其范围的末端停止。如果同时设置了该选项和[repeat](repeat.zh-Hans.md)，则该选项优先。

## 获取渐变选项

- **linearColor**：在线性色彩空间中对颜色进行内插的选项。
- **repeat**：在标称范围外重复渐变的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/GradientOptions/mirror
crawled: 2025-12-03T17:19:54Z
---

# mirror

**Type Property**

An option that repeats the gradient outside its nominal range, reflecting every other instance.

## Declaration

```swift
static var mirror: GraphicsContext.GradientOptions { get }
```

## Discussion

Use this option to cause the gradient to repeat its pattern in areas that exceed the bounds of its start and end points. The repetitions alternately reverse the start and end points, producing a pattern like `0 -> 1`, `1 -> 0`, `0 -> 1`, and so on.

Without either this option or [repeat](repeat.zh-Hans.md), the gradient stops at the end of its range. This option takes precendence if you set both this one and [repeat](repeat.zh-Hans.md).

## Getting gradient options

- **linearColor**: An option that interpolates between colors in a linear color space.
- **repeat**: An option that repeats the gradient outside its nominal range.

