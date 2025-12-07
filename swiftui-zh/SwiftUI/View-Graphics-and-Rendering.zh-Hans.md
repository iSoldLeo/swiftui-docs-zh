--- 来源：https://developer.apple.com/documentation/SwiftUI/View-Graphics-and-Rendering
抓取时间：2025-12-02T17:22:15Z

---

# 图形和渲染修饰符

**API 集合**

影响系统绘制视图的方式，例如缩放或遮罩视图，或应用图形效果。

## 概述

使用这些视图修饰符可以应用许多通常与图形上下文相关的渲染效果，例如添加遮罩和创建合成图像。您可以将这些效果应用于图形视图（例如 [Shapes](Shapes.zh-Hans.md)）以及任何其他 SwiftUI 视图。

如果您确实需要在图形上下文中使用即时模式绘制的灵活性，请改用 [Canvas](Canvas.zh-Hans.md) 视图。当您想要绘制大量动态形状时（例如，创建粒子效果），这将特别有用。

有关如何在应用中使用这些效果的更多信息，请参阅 [Drawing-and-graphics](Drawing-and-graphics.zh-Hans.md)。

## 遮罩和裁剪

- **mask(alignment:_:)**：使用给定视图的 Alpha 通道遮罩此视图。

- **clipped(antialiased:)**：将此视图裁剪到其边界矩形框内。

- **clipShape(_:style:)**：为此视图设置裁剪形状。

- **containerShape(_:)**：设置此视图内任何容器相对形状或同心矩形所使用的容器形状。

## 缩放

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **imageScale(_:)**：根据可用的相对尺寸（包括小、中、大图像尺寸）缩放视图中的图像。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

## 旋转和变换

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:anchor:)**：将视图内容按指定的 3D 旋转值旋转。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:axis:anchor:)**：将视图内容绕您指定的元素元组轴旋转一定角度。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图内容渲染成绕指定轴在三维空间中旋转后的样子。

- **projectionEffect(_:)**：对视图的渲染输出应用投影变换。

- **transformEffect(_:)**：对视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对视图的渲染输出应用 3D 变换。

## 图形效果

- **blur(radius:opaque:)**：对此视图应用高斯模糊。

- **opacity(_:)**：设置此视图的透明度。

- **brightness(_:)**：按指定量提高此视图的亮度。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：对此视图应用色调旋转效果。

- **luminanceToAlpha()**：对此视图添加亮度到透明度效果。

- **shadow(color:radius:x:y:)**：对此视图添加阴影。

- **visualEffect(_:)**：对此视图应用效果，同时通过几何代理提供对布局信息的访问。

- **visualEffect3D(_:)**：对此视图应用效果，同时通过 3D 几何代理提供对布局信息的访问。

## 着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 作为滤镜效果应用于每个像素的颜色。

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 应用于 `self`，作为几何扭曲效果作用于每个像素的位置。

- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 应用于 `self`，作为滤镜作用于由 `self` 创建的栅格图层。

## 合成

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **compositingGroup()**：将此视图包装在一个合成组中。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

## 动画

- **animation(_:)**：当此视图更改时，将指定的动画应用于此视图。

- **animation(_:value:)**：当指定值更改时，将指定的动画应用于此视图。

- **animation(_:body:)**：将指定的动画应用于 `body` 闭包内的所有可动画值。

- **keyframeAnimator(initialValue:repeating:content:keyframes:)**：循环播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **keyframeAnimator(initialValue:trigger:content:keyframes:)**：当指定的触发值更改时，播放指定的关键帧，并使用您在 `body` 中应用的修改器更新视图。

- **phaseAnimator(_:content:animation:)**：为视图应用的效果添加动画，使其在连续变化的阶段序列中呈现。

- **phaseAnimator(_:trigger:content:animation:)**：为视图应用的效果添加动画，使其在基于触发器变化的阶段序列中呈现。

- **contentTransition(_:)**：修改视图，使其使用指定的过渡效果作为视图内容动画的实现方式。

- **transition(_:)**：将过渡效果与视图关联。

- **transaction(_:)**：将指定的事务变更函数应用于视图中使用的所有动画。

- **transaction(value:_:)**：将指定的事务变更函数应用于视图中使用的所有动画。

- **transaction(_:body:)**：将给定的事务变更函数应用于 `body` 闭包中使用的所有动画。

- **contentTransition(_:)**：修改视图，使其使用给定的过渡效果作为其视图内容动画更改的方法。

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**：使用您提供的标识符和命名空间定义一组具有同步几何体的视图。

- **geometryGroup()**：将视图的几何体（例如位置和大小）与其父视图隔离。

## 绘图视图

- **样式修改器**：将内置样式应用于不同类型的视图。

- **布局修改器**：通过调整视图的大小、位置、对齐方式、内边距等，告诉视图如何在视图层次结构中排列自身。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Graphics-and-Rendering
crawled: 2025-12-02T17:22:15Z
---

# Graphics and rendering modifiers

**API Collection**

Affect the way the system draws a view, for example by scaling or masking a view, or by applying graphical effects.

## Overview

Use these view modifiers to apply many of the rendering effects typically associated with a graphics context, like adding masks and creating composites. You can apply these effects to graphical views, like [Shapes](Shapes.zh-Hans.md), as well as any other SwiftUI view.

When you do need the flexibility of immediate mode drawing in a graphics context, use a [Canvas](Canvas.zh-Hans.md) view instead. This can be particularly helpful when you want to draw an extremely large number of dynamic shapes — for example, to create particle effects.

For more information about using these effects in your app, see [Drawing-and-graphics](Drawing-and-graphics.zh-Hans.md).

## Masks and clipping

- **mask(alignment:_:)**: Masks this view using the alpha channel of the given view.
- **clipped(antialiased:)**: Clips this view to its bounding rectangular frame.
- **clipShape(_:style:)**: Sets a clipping shape for this view.
- **containerShape(_:)**: Sets the container shape to use for any container relative shape or concentric rectangle within this view.

## Scale

- **scaledToFill()**: Scales this view to fill its parent.
- **scaledToFit()**: Scales this view to fit its parent.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales this view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.
- **imageScale(_:)**: Scales images within the view according to one of the relative sizes available including small, medium, and large images sizes.
- **aspectRatio(_:contentMode:)**: Constrains this view’s dimensions to the specified aspect ratio.

## Rotation and transformation

- **rotationEffect(_:anchor:)**: Rotates a view’s rendered output in two dimensions around the specified point.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.

## Graphical effects

- **blur(radius:opaque:)**: Applies a Gaussian blur to this view.
- **opacity(_:)**: Sets the transparency of this view.
- **brightness(_:)**: Brightens this view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **shadow(color:radius:x:y:)**: Adds a shadow to this view.
- **visualEffect(_:)**: Applies effects to this view, while providing access to layout information through a geometry proxy.
- **visualEffect3D(_:)**: Applies effects to this view, while providing access to layout information through a 3D geometry proxy.

## Shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.

## Composites

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.

## Animations

- **animation(_:)**: Applies the given animation to this view when this view changes.
- **animation(_:value:)**: Applies the given animation to this view when the specified value changes.
- **animation(_:body:)**: Applies the given animation to all animatable values within the `body` closure.
- **keyframeAnimator(initialValue:repeating:content:keyframes:)**: Loops the given keyframes continuously, updating the view using the modifiers you apply in `body`.
- **keyframeAnimator(initialValue:trigger:content:keyframes:)**: Plays the given keyframes when the given trigger value changes, updating the view using the modifiers you apply in `body`.
- **phaseAnimator(_:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change continuously.
- **phaseAnimator(_:trigger:content:animation:)**: Animates effects that you apply to a view over a sequence of phases that change based on a trigger.
- **contentTransition(_:)**: Modifies the view to use a given transition as its method of animating changes to the contents of its views.
- **transition(_:)**: Associates a transition with the view.
- **transaction(_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(value:_:)**: Applies the given transaction mutation function to all animations used within the view.
- **transaction(_:body:)**: Applies the given transaction mutation function to all animations used within the `body` closure.
- **contentTransition(_:)**: Modifies the view to use a given transition as its method of animating changes to the contents of its views.
- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**: Defines a group of views with synchronized geometry using an identifier and namespace that you provide.
- **geometryGroup()**: Isolates the geometry (e.g. position and size) of the view from its parent view.

## Drawing views

- **Style modifiers**: Apply built-in styles to different types of views.
- **Layout modifiers**: Tell a view how to arrange itself within a view hierarchy by adjusting its size, position, alignment, padding, and so on.

