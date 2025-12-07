---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/brightness(_:)
抓取时间： 2025-12-01T22:05:44Z
---

# brightness(_:)

**类型方法**

返回应用亮度调整的过滤器。

## 声明

```swift
static func brightness(_ amount: Double) -> GraphicsContext.Filter
```

## 参数

- **amount**：要添加到像素颜色分量中的数值。

## 返回值

应用亮度调整的滤镜。

## 讨论

该滤镜与可缩放矢量图形（SVG）规范定义的`brightness`滤镜基元不同。您可以使用[grayscale(_:)](grayscale.zh-Hans.md) 颜色乘法获得类似该滤镜的效果。不过，该滤镜的亮度调整效果与[doc://com.apple.documentation/documentation/CoreImage/CIColorControls]滤镜一致。

## 更改亮度和对比度

- **contrast(_:)**：返回应用对比度调整的滤镜。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Filter/brightness(_:)
crawled: 2025-12-01T22:05:44Z
---

# brightness(_:)

**Type Method**

Returns a filter that applies a brightness adjustment.

## Declaration

```swift
static func brightness(_ amount: Double) -> GraphicsContext.Filter
```

## Parameters

- **amount**: An amount to add to the pixel’s color components.

## Return Value

A filter that applies a brightness adjustment.

## Discussion

This filter is different than `brightness` filter primitive defined by the Scalable Vector Graphics (SVG) specification. You can obtain an effect like that filter using a [grayscale(_:)](grayscale.zh-Hans.md) color multiply. However, this filter does match the [doc://com.apple.documentation/documentation/CoreImage/CIColorControls] filter’s brightness adjustment.

## Changing brightness and contrast

- **contrast(_:)**: Returns a filter that applies a contrast adjustment.

