---
来源：https://developer.apple.com/documentation/SwiftUI/VisualEffect/blur(radius:opaque:)
抓取时间：2025-12-03T06:30:02Z
---

# blur(radius:opaque:)

**实例方法**

对视图进行高斯模糊处理。

## 声明

```swift
func blur(radius: CGFloat, opaque: Bool = false) -> some VisualEffect

```

## 参数

- **radius**：模糊的径向大小。半径越大，模糊效果越分散。
- **opaque**：布尔值，表示模糊渲染器是否允许在模糊输出中使用透明度。设置为 `true`可创建不透明的模糊效果，设置为 `false`则允许透明效果。

## 返回值

模糊视图的效果。

## 讨论

使用 `blur(radius:opaque:)` 可以在渲染视图时应用高斯模糊效果。

## 应用其他效果

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新的视觉效果，将`shader`应用到`self`，作为每个像素位置的几何扭曲效果。
- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一种新的视觉效果，在由`self` 创建的栅格图层上将`shader` 作为滤镜应用到`self`。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/blur(radius:opaque:)
crawled: 2025-12-03T06:30:02Z
---

# blur(radius:opaque:)

**Instance Method**

Applies a Gaussian blur to the view.

## Declaration

```swift
func blur(radius: CGFloat, opaque: Bool = false) -> some VisualEffect

```

## Parameters

- **radius**: The radial size of the blur. A blur is more diffuse when its radius is large.
- **opaque**: A Boolean value that indicates whether the blur renderer permits transparency in the blur output. Set to `true` to create an opaque blur, or set to `false` to permit transparency.

## Return Value

An effect that blurs the view.

## Discussion

Use `blur(radius:opaque:)` to apply a gaussian blur effect to the rendering of the view.

## Applying other effects

- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter on the raster layer created from `self`.

