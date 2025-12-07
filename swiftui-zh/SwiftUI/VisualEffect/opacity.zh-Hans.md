---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/opacity(_:)
抓取时间： 2025-12-01T11:18:58Z
---

# 不透明度(_:)

**实例方法**

设置视图的透明度。

## 声明

```swift
func opacity(_ opacity: Double) -> some VisualEffect

```

## 参数

- **opacity**：介于 0（完全透明）和 1（完全不透明）之间的值。

## 返回值

设置视图透明度的效果。

## 讨论

当对已经进行过不透明度变换的视图应用`opacity(_:)` 效果时，底层不透明度变换的效果会被乘以。

## 调整颜色

- **brightness(_:)**：按指定量增亮视图。
- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分离度。
- **grayscale(_:)**：为视图添加灰度效果。
- **hueRotation(_:)**：为视图应用色调旋转效果。
- **saturation(_:)**：调整视图的色彩饱和度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/opacity(_:)
crawled: 2025-12-01T11:18:58Z
---

# opacity(_:)

**Instance Method**

Sets the transparency of the view.

## Declaration

```swift
func opacity(_ opacity: Double) -> some VisualEffect

```

## Parameters

- **opacity**: A value between 0 (fully transparent) and 1 (fully opaque).

## Return Value

An effect that sets the transparency of the view.

## Discussion

When applying the `opacity(_:)` effect to a view that has already had its opacity transformed, the effect of the underlying opacity transformation is multiplied.

## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.

