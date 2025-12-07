--- 来源：https://developer.apple.com/documentation/SwiftUI/Drawing-and-graphics

抓取时间：2025-12-02T16:02:53Z

---

# 绘图和图形

**API 集合**

使用图形效果和自定义绘图增强您的视图。

## 概述

您可以使用 SwiftUI 提供的内置视图和 [Shapes](Shapes.zh-Hans.md) 创建丰富、动态的用户界面。为了增强任何视图，您可以应用许多通常与图形上下文关联的图形效果，例如设置颜色、添加蒙版和创建合成图形。

当您需要在图形上下文中使用即时模式绘图的灵活性时，请使用 [Canvas](Canvas.zh-Hans.md) 视图。当您想要绘制大量动态形状时（例如，创建粒子效果），这将特别有用。

设计指南请参见《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/materials] 和 [doc://com.apple.documentation/design/Human-Interface-Guidelines/color]。

## 即时模式绘制

- **为您的 SwiftUI 应用添加丰富的图形**：通过添加背景材质、鲜艳度、自定义图形和动画，让您的应用脱颖而出。

- **Canvas**：支持即时模式绘制的视图类型。

- **GraphicsContext**：即时模式绘制的目标位置及其当前状态。

## 设置颜色

- **tint(_:)**：设置此视图的色调颜色。

- **Color**：一种能够适应给定上下文的颜色表示形式。

## 设置内容样式

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。

- **foregroundStyle(_:)**：设置视图的前景色元素使用指定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景色样式的主样式和次样式级别。

- **foregroundStyle(_:_:_:)**：设置前景色样式的主样式、次样式和三级样式。

- **backgroundStyle(_:)**：设置指定的样式以渲染视图中的背景。

- **backgroundStyle**：可选样式，设置后会覆盖默认的系统背景样式。

- **ShapeStyle**：渲染形状时使用的颜色或图案。

- **AnyShapeStyle**：已擦除类型的 ShapeStyle 值。

- **Gradient**：以颜色停止点数组表示的颜色渐变，每个停止点都有一个参数化的位置值。

- **MeshGradient**：由二维定位颜色网格定义的二维渐变。

- **AnyGradient**：颜色渐变。

- **ShadowStyle**：用于渲染阴影的样式。

- **Glass**：定义液态玻璃材质配置的结构。

## 颜色变换

- **brightness(_:)**：按指定量提亮此视图。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为该视图添加颜色乘法效果。

- **saturation(_:)**：调整该视图的颜色饱和度。

- **grayscale(_:)**：为该视图添加灰度效果。

- **hueRotation(_:)**：为该视图应用色相旋转效果。

- **luminanceToAlpha()**：为该视图添加亮度到透明度 (Alpha) 转换效果。

- **materialActiveAppearance(_:)**：为该视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质在其激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。

## 缩放、旋转或变换视图

- **scaledToFill()**：缩放此视图以填充其父视图。

- **scaledToFit()**：缩放此视图以适应其父视图。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(_:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:anchor:)**：相对于锚点，按给定的水平和垂直比例缩放此视图的渲染输出。

- **scaleEffect(x:y:z:anchor:)**：相对于锚点，按指定的水平、垂直和深度因子缩放此视图。

- **aspectRatio(_:contentMode:)**：将此视图的尺寸限制为指定的宽高比。

- **rotationEffect(_:anchor:)**：围绕指定点在二维空间中旋转视图的渲染输出。

- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**：将视图的内容渲染成围绕指定轴在三维空间中旋转后的样子。

- **rotation3DEffect(_:anchor:)**：将视图的内容旋转指定的三维旋转值。

- **rotation3DEffect(_:axis:anchor:)**：将视图的内容绕您指定的元素元组轴旋转指定的角度。

- **transformEffect(_:)**：对当前视图的渲染输出应用仿射变换。

- **transform3DEffect(_:)**：对当前视图的渲染输出应用三维变换。

- **projectionEffect(_:)**：对当前视图的渲染输出应用投影变换。

- **ProjectionTransform**

- **ContentMode**：定义视图内容如何填充可用空间的常量。

## 遮罩和裁剪

- **mask(alignment:_:)**：使用给定视图的 Alpha 通道遮罩当前视图。

- **clipped(antialiased:)**：将当前视图裁剪到其边界矩形框。

- **clipShape(_:style:)**：设置当前视图的裁剪形状。

## 应用模糊和阴影

- **blur(radius:opaque:)**：对此视图应用高斯模糊。

- **shadow(color:radius:x:y:)**：为此视图添加阴影。

- **ColorMatrix**：用于 RGBA 颜色变换的矩阵。

## 应用基于几何体的效果

- **visualEffect(_:)**：对此视图应用效果，同时通过几何体代理提供对布局信息的访问。

- **visualEffect3D(_:)**：对此视图应用效果，同时通过 3D 几何体代理提供对布局信息的访问。

- **VisualEffect**：视觉效果会在不更改其父视图或子视图的情况下更改视图的视觉外观。

- **EmptyVisualEffect**：要应用其他效果的基础视觉效果。

## 合成视图

- **blendMode(_:)**：设置此视图与重叠视图合成的混合模式。

- **compositingGroup()**：将此视图包装在合成组中。

- **drawingGroup(opaque:colorMode:)**：在最终显示之前，将此视图的内容合成到屏幕外图像中。

- **BlendMode**：用于合成包含重叠内容的视图的模式。

- **ColorRenderingMode**：用于颜色合成操作的可用颜色空间集。

- **CompositorContent**

- **CompositorContentBuilder**：用于合成 [CompositorContent](CompositorContent.zh-Hans.md) 元素集合的结果构建器。

- **AnyCompositorContent**：类型擦除合成器内容。

## 测量视图

- **GeometryReader**：容器视图，其内容定义为自身大小和坐标空间的函数。

- **GeometryReader3D**：容器视图，其内容定义为自身大小和坐标空间的函数。

- **GeometryProxy**：用于访问容器视图的大小和坐标空间（用于锚点解析）的代理。

- **GeometryProxy3D**：用于访问容器视图的大小和坐标空间的代理。

- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和大小等维度。

- **CoordinateSpace**：由坐标空间协议创建的已解析坐标空间。

- **CoordinateSpaceProtocol**：布局系统中的参考系。

- **PhysicalMetric**：提供对与指定物理测量值对应的点值的访问。

- **PhysicalMetricsConverter**：物理度量转换器，提供点值与其在三维空间中的范围（以物理长度测量值的形式）之间的转换。

## 响应几何体变化

- **onGeometryChange(for:of:action:)**：添加当由几何代理创建的值发生变化时要执行的操作。

## 访问 Metal 着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的颜色，作为滤镜效果。

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的位置，作为几何扭曲效果。

- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于由 `self` 创建的栅格图层，作为滤镜效果。

- **Shader**：指向 Metal 着色器库中函数的引用，以及其绑定的 uniform 参数值。

- **ShaderFunction**：指向 Metal 着色器库中函数的引用。

- **ShaderLibrary**：Metal 着色器库。

## 访问几何结构

- **Axis**：二维坐标系中的水平或垂直维度。

- **Angle**：几何角度，其值可以以弧度或角度表示。

- **UnitPoint**：视图坐标空间中的归一化二维点。

- **UnitPoint3D**：视图坐标空间中的归一化三维点。

- **Anchor**：从锚点源和特定视图派生的不透明值。

- **DepthAlignmentID**

- **Alignment3D**：三个轴的对齐。

- **GeometryProxyCoordinateSpace3D**：`GeometryProxy3D` 的表示形式，可用于基于 `CoordinateSpace3D` 的转换。

## 视图

- **视图基础**：使用视图层级结构定义应用程序的视觉元素。

- **视图配置**：调整层级结构中视图的特性。

- **视图样式**：将内置和自定义的外观及行为应用于不同类型的视图。

- **Animations**：响应状态变化，实现平滑的视觉更新。

- **文本输入和输出**：显示格式化文本并接收用户输入的文本。

- **Images**：向应用程序的用户界面添加图像和符号。

- **控件和指示器**：显示数值并获取用户选择。

- **菜单和命令**：提供节省空间且上下文相关的命令和控件访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘并填充内置和自定义形状。


---
source: https://developer.apple.com/documentation/SwiftUI/Drawing-and-graphics
crawled: 2025-12-02T16:02:53Z
---

# Drawing and graphics

**API Collection**

Enhance your views with graphical effects and customized drawings.

## Overview

You create rich, dynamic user interfaces with the built-in views and [Shapes](Shapes.zh-Hans.md) that SwiftUI provides. To enhance any view, you can apply many of the graphical effects typically associated with a graphics context, like setting colors, adding masks, and creating composites.



When you need the flexibility of immediate mode drawing in a graphics context, use a [Canvas](Canvas.zh-Hans.md) view. This can be particularly helpful when you want to draw an extremely large number of dynamic shapes — for example, to create particle effects.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/materials] and [doc://com.apple.documentation/design/Human-Interface-Guidelines/color] in the Human Interface Guidelines.

## Immediate mode drawing

- **Add rich graphics to your SwiftUI app**: Make your apps stand out by adding background materials, vibrancy, custom graphics, and animations.
- **Canvas**: A view type that supports immediate mode drawing.
- **GraphicsContext**: An immediate mode drawing destination, and its current state.

## Setting a color

- **tint(_:)**: Sets the tint color within this view.
- **Color**: A representation of a color that adapts to a given context.

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **ShapeStyle**: A color or pattern to use when rendering a shape.
- **AnyShapeStyle**: A type-erased ShapeStyle value.
- **Gradient**: A color gradient represented as an array of color stops, each having a parametric location value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **AnyGradient**: A color gradient.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

## Transforming colors

- **brightness(_:)**: Brightens this view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

## Scaling, rotating, or transforming a view

- **scaledToFill()**: Scales this view to fill its parent.
- **scaledToFit()**: Scales this view to fit its parent.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(_:anchor:)**: Scales this view’s rendered output by the given amount in both the horizontal and vertical directions, relative to an anchor point.
- **scaleEffect(x:y:anchor:)**: Scales this view’s rendered output by the given horizontal and vertical amounts, relative to an anchor point.
- **scaleEffect(x:y:z:anchor:)**: Scales this view by the specified horizontal, vertical, and depth factors, relative to an anchor point.
- **aspectRatio(_:contentMode:)**: Constrains this view’s dimensions to the specified aspect ratio.
- **rotationEffect(_:anchor:)**: Rotates a view’s rendered output in two dimensions around the specified point.
- **rotation3DEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **perspectiveRotationEffect(_:axis:anchor:anchorZ:perspective:)**: Renders a view’s content as if it’s rotated in three dimensions around the specified axis.
- **rotation3DEffect(_:anchor:)**: Rotates the view’s content by the specified 3D rotation value.
- **rotation3DEffect(_:axis:anchor:)**: Rotates the view’s content by an angle about an axis that you specify as a tuple of elements.
- **transformEffect(_:)**: Applies an affine transformation to this view’s rendered output.
- **transform3DEffect(_:)**: Applies a 3D transformation to this view’s rendered output.
- **projectionEffect(_:)**: Applies a projection transformation to this view’s rendered output.
- **ProjectionTransform**
- **ContentMode**: Constants that define how a view’s content fills the available space.

## Masking and clipping

- **mask(alignment:_:)**: Masks this view using the alpha channel of the given view.
- **clipped(antialiased:)**: Clips this view to its bounding rectangular frame.
- **clipShape(_:style:)**: Sets a clipping shape for this view.

## Applying blur and shadows

- **blur(radius:opaque:)**: Applies a Gaussian blur to this view.
- **shadow(color:radius:x:y:)**: Adds a shadow to this view.
- **ColorMatrix**: A matrix to use in an RGBA color transformation.

## Applying effects based on geometry

- **visualEffect(_:)**: Applies effects to this view, while providing access to layout information through a geometry proxy.
- **visualEffect3D(_:)**: Applies effects to this view, while providing access to layout information through a 3D geometry proxy.
- **VisualEffect**: Visual Effects change the visual appearance of a view without changing its ancestors or descendents.
- **EmptyVisualEffect**: The base visual effect that you apply additional effect to.

## Compositing views

- **blendMode(_:)**: Sets the blend mode for compositing this view with overlapping views.
- **compositingGroup()**: Wraps this view in a compositing group.
- **drawingGroup(opaque:colorMode:)**: Composites this view’s contents into an offscreen image before final display.
- **BlendMode**: Modes for compositing a view with overlapping content.
- **ColorRenderingMode**: The set of possible working color spaces for color-compositing operations.
- **CompositorContent**
- **CompositorContentBuilder**: A result builder for composing a collection of [CompositorContent](CompositorContent.zh-Hans.md) elements.
- **AnyCompositorContent**: Type erased compositor content.

## Measuring a view

- **GeometryReader**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryReader3D**: A container view that defines its content as a function of its own size and coordinate space.
- **GeometryProxy**: A proxy for access to the size and coordinate space (for anchor resolution) of the container view.
- **GeometryProxy3D**: A proxy for access to the size and coordinate space of the container view.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.
- **CoordinateSpace**: A resolved coordinate space created by the coordinate space protocol.
- **CoordinateSpaceProtocol**: A frame of reference within the layout system.
- **PhysicalMetric**: Provides access to a value in points that corresponds to the specified physical measurement.
- **PhysicalMetricsConverter**: A physical metrics converter provides conversion between point values and their extent in 3D space, in the form of physical length measurements.

## Responding to a geometry change

- **onGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a geometry proxy, changes.

## Accessing Metal shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.
- **Shader**: A reference to a function in a Metal shader library, along with its bound uniform argument values.
- **ShaderFunction**: A reference to a function in a Metal shader library.
- **ShaderLibrary**: A Metal shader library.

## Accessing geometric constructs

- **Axis**: The horizontal or vertical dimension in a 2D coordinate system.
- **Angle**: A geometric angle whose value you access in either radians or degrees.
- **UnitPoint**: A normalized 2D point in a view’s coordinate space.
- **UnitPoint3D**: A normalized 3D point in a view’s coordinate space.
- **Anchor**: An opaque value derived from an anchor source and a particular view.
- **DepthAlignmentID**
- **Alignment3D**: An alignment in all three axes.
- **GeometryProxyCoordinateSpace3D**: A representation of a `GeometryProxy3D` which can be used for `CoordinateSpace3D` based conversions.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.

