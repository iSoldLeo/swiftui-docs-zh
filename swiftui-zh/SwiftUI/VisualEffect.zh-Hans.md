---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect
抓取时间： 2025-12-02T17:37:28Z
---

# VisualEffect

**Protocol**

视觉效果可以改变视图的视觉外观，而不会改变其祖先或后代。

## 声明

```swift
protocol VisualEffect : Sendable, Animatable
```

## 概览

由于特效不会影响布局，因此可以在不允许修改布局的情况下安全使用。例如，特效可以作为位置函数应用，通过几何体代理访问：

```swift
var body: some View {
    ContentRow()
        .visualEffect { content, geometryProxy in
            content.offset(x: geometryProxy.frame(in: .global).origin.y)
        }
}
```

你自己并不遵守这一协议。相反，视觉效果是通过调用修改器函数（如上例中的`.offset(x:y:)`）来创建的。

### 调整颜色

- **brightness(_:)**：按指定数量增亮视图。
- **colorEffect(_:isEnabled:)**：返回一个新的视觉效果，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分离度。
- **grayscale(_:)**：为视图添加灰度效果。
- **hueRotation(_:)**：为视图应用色调旋转效果。
- **saturation(_:)**：调整视图的色彩饱和度。
- **opacity(_:)**：设置视图的透明度。

## 缩放

- **scaleEffect(_:anchor:)**：相对于一个锚点，以指定的系数均匀地缩放该视图。
- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直量缩放视图的渲染输出。
- **scaleEffect(x:y:z:anchor:)**：根据指定的水平、垂直和深度因子，相对于锚点缩放该视图。

## 旋转

- **rotationEffect(_:anchor:)**：围绕指定点从两个维度旋转内容。
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将内容渲染为围绕指定轴线的三维旋转。
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**：以三维方式围绕指定轴旋转渲染内容。
- **rotation3DEffect(_:anchor:)**：按指定的三维旋转值旋转内容。
- **rotation3DEffect(_:axis:anchor:)**：以您指定的元素元组为轴旋转内容一个角度。

## 翻译

- **offset(_:)**：按照偏移参数中指定的水平和垂直量偏移视图。
- **offset(x:y:)**：按指定的水平和垂直距离偏移视图。
- **offset(z:)**：以点为单位将视图在 Z 轴向前移动指定的距离。

## 应用变换

- **transform3DEffect(_:)**：对该视图的渲染输出应用 3D 变换。
- **transformEffect(_:)**：将仿射变换应用到该视图的渲染输出。

## 应用其他特效

- **blur(radius:opaque:)**：对视图应用高斯模糊。
- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新的视觉效果，将`shader`应用到`self`，作为每个像素位置的几何扭曲效果。
- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回将`shader` 应用到`self` 的新视觉效果，作为`self` 创建的栅格图层上的滤镜。

### 实例方法

- **blendMode(_:)**：设置混合模式，以便将此视图与重叠视图合成。

## 基于几何图形应用特效

- **visualEffect(_:)**：在此视图中应用特效，同时通过几何体代理访问布局信息。
- **visualEffect3D(_:)**：在此视图中应用特效，同时通过 3D 几何图形代理提供对布局信息的访问。
- **EmptyVisualEffect**：基础视觉效果，您可以将附加效果应用到它。

## 继承自

- 动画效果
- 可发送
- 可发送元类型

## 符合类型

- 空视觉效果
- 修改内容


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect
crawled: 2025-12-02T17:37:28Z
---

# VisualEffect

**Protocol**

Visual Effects change the visual appearance of a view without changing its ancestors or descendents.

## Declaration

```swift
protocol VisualEffect : Sendable, Animatable
```

## Overview

Because effects do not impact layout, they are safe to use in situations where layout modification is not allowed. For example, effects may be applied as a function of position, accessed through a geometry proxy:

```swift
var body: some View {
    ContentRow()
        .visualEffect { content, geometryProxy in
            content.offset(x: geometryProxy.frame(in: .global).origin.y)
        }
}
```

You don’t conform to this protocol yourself. Instead, visual effects are created by calling modifier functions (such as `.offset(x:y:)` on other effects, as seen in the example above.

## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **colorEffect(_:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.
- **opacity(_:)**: Sets the transparency of the view.

## Scaling

- **scaleEffect(_:anchor:)**: Scales this view uniformly by the specified factor, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales the view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.

## Rotating

- **rotationEffect(_:anchor:)**: Rotates content in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:perspective:)**: Renders content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates content by an angle about an axis that you specify as a tuple of elements.

## Translating

- **offset(_:)**: Offsets the view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offsets the view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

## Applying a transform

- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **transformEffect(_:)**: Applies an affine transformation to the view’s rendered output.

## Applying other effects

- **blur(radius:opaque:)**: Applies a Gaussian blur to the view.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new visual effect that applies `shader` to `self` as a filter on the raster layer created from `self`.

## Instance Methods

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.

## Applying effects based on geometry

- **visualEffect(_:)**: Applies effects to this view, while providing access to layout information through a geometry proxy.
- **visualEffect3D(_:)**: Applies effects to this view, while providing access to layout information through a 3D geometry proxy.
- **EmptyVisualEffect**: The base visual effect that you apply additional effect to.

## Inherits From

- Animatable
- Sendable
- SendableMetatype

## Conforming Types

- EmptyVisualEffect
- ModifiedContent

