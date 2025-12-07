---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/GradientOptions/repeat
抓取时间： 2025-12-03T17:19:55Z
---

# 重复

**类型属性**

在标称范围外重复渐变的选项。

## 声明

```swift
static var `repeat`: GraphicsContext.GradientOptions { get }
```

## 讨论

使用此选项可使渐变在超出起点和终点范围的区域重复其图案。每次重复都使用相同的起点和终点值。

如果没有此选项或[mirror](mirror.zh-Hans.md)，渐变将在其范围的末端停止。如果同时设置[mirror](mirror.zh-Hans.md) 和[mirror](mirror.zh-Hans.md) 选项，则[mirror](mirror.zh-Hans.md) 选项优先。

## 获取渐变选项

- **linearColor**：在线性色彩空间中对颜色进行内插的选项。
- **mirror**：在标称范围外重复渐变的选项，每隔一个实例就会出现一次。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/GradientOptions/repeat
crawled: 2025-12-03T17:19:55Z
---

# repeat

**Type Property**

An option that repeats the gradient outside its nominal range.

## Declaration

```swift
static var `repeat`: GraphicsContext.GradientOptions { get }
```

## Discussion

Use this option to cause the gradient to repeat its pattern in areas that exceed the bounds of its start and end points. The repetitions use the same start and end value for each repetition.

Without this option or [mirror](mirror.zh-Hans.md), the gradient stops at the end of its range. The [mirror](mirror.zh-Hans.md) option takes precendence if you set both this one and that one.

## Getting gradient options

- **linearColor**: An option that interpolates between colors in a linear color space.
- **mirror**: An option that repeats the gradient outside its nominal range, reflecting every other instance.

