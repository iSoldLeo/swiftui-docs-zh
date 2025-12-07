---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/brightness(_:)
抓取时间： 2025-12-03T06:29:45Z
---

# brightness(_:)

**实例方法**

按指定的亮度增亮视图。

## 声明

```swift
func brightness(_ amount: Double) -> some VisualEffect

```

## 参数

- **amount**：介于 0（无效果）和 1（全白增亮）之间的值，表示亮度效果的强度。

## 返回值

按指定数量增亮视图的效果。

## 调整颜色

- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分离度。
- **grayscale(_:)**：为视图添加灰度效果。
- **hueRotation(_:)**：为视图应用色调旋转效果。
- **saturation(_:)**：调整视图的色彩饱和度。
- **opacity(_:)**：设置视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/brightness(_:)
crawled: 2025-12-03T06:29:45Z
---

# brightness(_:)

**Instance Method**

Brightens the view by the specified amount.

## Declaration

```swift
func brightness(_ amount: Double) -> some VisualEffect

```

## Parameters

- **amount**: A value between 0 (no effect) and 1 (full white brightening) that represents the intensity of the brightness effect.

## Return Value

An effect that brightens the view by the specified amount.

## Adjusting Color

- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.
- **opacity(_:)**: Sets the transparency of the view.

