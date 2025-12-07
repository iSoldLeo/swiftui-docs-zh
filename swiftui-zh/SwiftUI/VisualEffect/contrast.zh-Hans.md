---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/contrast(_:)
抓取时间： 2025-12-01T11:18:54Z
---

# contrast(_:)

**实例方法**

设置视图中相似颜色之间的对比度和分隔度。

## 声明

```swift
func contrast(_ amount: Double) -> some VisualEffect

```

## 参数

- **amount**：要应用的颜色对比度的强度。负值除了应用对比度外，还会反转颜色。

## 返回值

对视图应用色彩对比度的效果。

## 讨论

在视图中应用对比度可增加或减少视图中相似颜色之间的间隔。

## 调整色彩

- **brightness(_:)**：按指定量增亮视图。
- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **grayscale(_:)**：为视图添加灰度效果。
- **hueRotation(_:)**：为视图应用色调旋转效果。
- **saturation(_:)**：调整视图的色彩饱和度。
- **opacity(_:)**：设置视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/contrast(_:)
crawled: 2025-12-01T11:18:54Z
---

# contrast(_:)

**Instance Method**

Sets the contrast and separation between similar colors in the view.

## Declaration

```swift
func contrast(_ amount: Double) -> some VisualEffect

```

## Parameters

- **amount**: The intensity of color contrast to apply. negative values invert colors in addition to applying contrast.

## Return Value

An effect that applies color contrast to the view.

## Discussion

Apply contrast to a view to increase or decrease the separation between similar colors in the view.

## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.
- **opacity(_:)**: Sets the transparency of the view.

