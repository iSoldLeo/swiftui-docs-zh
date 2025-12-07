---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/luminanceToAlpha
抓取时间： 2025-12-03T17:20:36Z
---

# luminanceToAlpha

**类型属性**

返回根据亮度设置每个像素不透明度的过滤器。

## 声明

```swift
static var luminanceToAlpha: GraphicsContext.Filter { get }
```

## 返回值

将亮度转换为 alpha 的滤波器。

## 讨论

该滤镜会计算每个像素的亮度，并用它来定义结果的不透明度，再加上黑色（零）颜色成分。

## 调整不透明度

- **alphaThreshold(min:max:color:)**：返回一个滤镜，在一定范围内用常量颜色替换每个像素的 alpha 分量，否则返回透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/luminanceToAlpha
crawled: 2025-12-03T17:20:36Z
---

# luminanceToAlpha

**Type Property**

Returns a filter that sets the opacity of each pixel based on its luminance.

## Declaration

```swift
static var luminanceToAlpha: GraphicsContext.Filter { get }
```

## Return Value

A filter that applies a luminance to alpha transformation.

## Discussion

The filter computes the luminance of each pixel and uses it to define the opacity of the result, combined with black (zero) color components.

## Adjusting opacity

- **alphaThreshold(min:max:color:)**: Returns a filter that replaces each pixel with alpha components within a range by a constant color, or transparency otherwise.

