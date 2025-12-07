---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/saturation(_:)
抓取时间： 2025-12-01T11:18:57Z
---

# 饱和度(_:)

**实例方法**

调整视图的色彩饱和度。

## 声明

```swift
func saturation(_ amount: Double) -> some VisualEffect

```

## 参数

- **amount**：要应用于视图的饱和度。

## 返回值

调整视图饱和度的效果。

## 讨论

使用色彩饱和度可以增加或减少视图中的色彩强度。



## 调整色彩

- **brightness(_:)**：按指定量增亮视图。
- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分离度。
- **grayscale(_:)**：为视图添加灰度效果。
- **hueRotation(_:)**：为视图应用色调旋转效果。
- **opacity(_:)**：设置视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/saturation(_:)
crawled: 2025-12-01T11:18:57Z
---

# saturation(_:)

**Instance Method**

Adjusts the color saturation of the view.

## Declaration

```swift
func saturation(_ amount: Double) -> some VisualEffect

```

## Parameters

- **amount**: The amount of saturation to apply to the view.

## Return Value

An effect that adjusts the saturation of the view.

## Discussion

Use color saturation to increase or decrease the intensity of colors in a view.



## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **opacity(_:)**: Sets the transparency of the view.

