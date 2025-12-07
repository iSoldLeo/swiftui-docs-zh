---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/grayscale(_:)
抓取时间： 2025-12-01T11:18:55Z
---

# Grayscale(_:)

**实例方法**

为视图添加灰度效果。

## 声明

```swift
func grayscale(_ amount: Double) -> some VisualEffect

```

## 参数

- **amount**：要应用的灰度强度，从 0.0 到小于 1.0。接近 0.0 的值色彩更丰富，接近 1.0 的值色彩较淡。

## 返回值

降低视图中色彩强度的效果。

## 讨论

灰度效果会降低视图中颜色的强度。

## 调整色彩

- **brightness(_:)**：按指定量增亮视图。
- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分离度。
- **hueRotation(_:)**：在视图中应用色调旋转效果。
- **saturation(_:)**：调整视图的色彩饱和度。
- **opacity(_:)**：设置视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/grayscale(_:)
crawled: 2025-12-01T11:18:55Z
---

# grayscale(_:)

**Instance Method**

Adds a grayscale effect to the view.

## Declaration

```swift
func grayscale(_ amount: Double) -> some VisualEffect

```

## Parameters

- **amount**: The intensity of grayscale to apply from 0.0 to less than 1.0. Values closer to 0.0 are more colorful, and values closer to 1.0 are less colorful.

## Return Value

An effect that reduces the intensity of colors in the view.

## Discussion

A grayscale effect reduces the intensity of colors in the view.

## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.
- **opacity(_:)**: Sets the transparency of the view.

