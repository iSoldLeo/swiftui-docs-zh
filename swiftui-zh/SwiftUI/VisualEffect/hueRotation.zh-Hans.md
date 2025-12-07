---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/hueRotation(_:)
抓取时间： 2025-12-03T06:29:47Z
---

# hueRotation(_:)

**实例方法**

为视图应用色调旋转效果。

## 声明

```swift
func hueRotation(_ angle: Angle) -> some VisualEffect

```

## 参数

- **angle**：应用于视图中颜色的色调旋转角度。

## 返回值

移动视图中所有颜色的效果。

## 讨论

使用色调旋转特效，可按照您指定的角度移动视图中的所有颜色。

## 调整色彩

- **brightness(_:)**：按指定的量增亮视图。
- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分离度。
- **grayscale(_:)**：为视图添加灰度效果。
- **saturation(_:)**：调整视图的色彩饱和度。
- **opacity(_:)**：设置视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/hueRotation(_:)
crawled: 2025-12-03T06:29:47Z
---

# hueRotation(_:)

**Instance Method**

Applies a hue rotation effect to the view.

## Declaration

```swift
func hueRotation(_ angle: Angle) -> some VisualEffect

```

## Parameters

- **angle**: The hue rotation angle to apply to the colors in the view.

## Return Value

An effect that shifts all of the colors in the view.

## Discussion

Use hue rotation effect to shift all of the colors in a view according to the angle you specify.

## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.
- **opacity(_:)**: Sets the transparency of the view.

