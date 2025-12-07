---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlurOptions/opaque
抓取时间： 2025-12-03T17:20:41Z
---

# 不透明

**类型属性**

使过滤器确保结果完全不透明的选项。

## 声明

```swift
static var opaque: GraphicsContext.BlurOptions { get }
```

## 讨论

滤镜通过将每个像素除以其 Alpha 值来确保不透明度。如果输入到滤镜的像素不是完全不透明，结果可能是未定义的。

## 获取模糊选项

- **dithersResult**：使滤波器对结果进行抖动的选项，以减少条带。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/BlurOptions/opaque
crawled: 2025-12-03T17:20:41Z
---

# opaque

**Type Property**

An option that causes the filter to ensure the result is completely opaque.

## Declaration

```swift
static var opaque: GraphicsContext.BlurOptions { get }
```

## Discussion

The filter ensure opacity by dividing each pixel by its alpha value. The result may be undefined if the input to the filter isn’t also completely opaque.

## Getting blur options

- **dithersResult**: An option that causes the filter to dither the result, to reduce banding.

