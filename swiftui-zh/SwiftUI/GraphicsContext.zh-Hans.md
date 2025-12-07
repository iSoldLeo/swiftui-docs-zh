---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext
抓取时间： 2025-12-02T16:15:44Z
---

# GraphicsContext

**Structure**

立即模式绘图目标及其当前状态。

## 声明

```swift
@frozen struct GraphicsContext
```

## 概览

使用上下文执行 2D 绘图基元。例如，您可以使用[fill(_:with:style:)](GraphicsContext/fill___with_style.zh-Hans.md) 方法在[Canvas](Canvas.zh-Hans.md) 视图中绘制填充形状：

```swift
Canvas { context, size in
    context.fill(
        Path(ellipseIn: CGRect(origin: .zero, size: size)),
        with: .color(.green))
}
.frame(width: 300, height: 200)
```方法

上面的示例绘制了一个椭圆，该椭圆刚好适合宽 300 点、高 200 点的画布：



除了勾画或填充路径外，还可以绘制图像、文本和 SwiftUI 视图。您还可以使用上下文执行许多常见的图形操作，如添加遮罩、应用滤镜和变换以及设置混合模式。例如，您可以使用[clip(to:style:options:)](GraphicsContext/clip_to_style_options.zh-Hans.md) 方法添加遮罩：

```swift
let halfSize = size.applying(CGAffineTransform(scaleX: 0.5, y: 0.5))
context.clip(to: Path(CGRect(origin: .zero, size: halfSize)))
context.fill(
    Path(ellipseIn: CGRect(origin: .zero, size: size)),
    with: .color(.green))
```

矩形遮罩隐藏了椭圆的所有部分，只有一个象限除外：



操作顺序很重要。对上下文状态所做的更改，如添加遮罩或滤镜，会应用到后面的绘图操作中。如果将上例中的填充和剪切操作颠倒一下，让填充先进行，蒙版就不会影响椭圆。

每个上下文都引用了透明度图层树中的一个特定图层，并包含绘图状态的完整副本。您可以修改一个上下文的状态，而不影响其他上下文的状态，即使它们引用的是同一图层。例如，您可以将上一示例中的遮罩椭圆绘制到主上下文的副本中，然后在主上下文中添加一个矩形：

```swift
// Create a copy of the context to draw a clipped ellipse.
var maskedContext = context
let halfSize = size.applying(CGAffineTransform(scaleX: 0.5, y: 0.5))
maskedContext.clip(to: Path(CGRect(origin: .zero, size: halfSize)))
maskedContext.fill(
    Path(ellipseIn: CGRect(origin: .zero, size: size)),
    with: .color(.green))

// Go back to the original context to draw the rectangle.
let origin = CGPoint(x: size.width / 4, y: size.height / 4)
context.fill(
    Path(CGRect(origin: origin, size: halfSize)),
    with: .color(.blue))
```

遮罩不会剪切矩形，因为遮罩不是主上下文的一部分。但是，两个上下文都绘制到同一个视图中，因为您将其中一个上下文创建为另一个上下文的副本：



上下文可以访问名为[EnvironmentValues](EnvironmentValues.zh-Hans.md) 的[environment](GraphicsContext/environment.zh-Hans.md) 实例，该实例最初是从其外层视图的环境中复制的。SwiftUI 使用环境值（如显示分辨率和配色方案）来解析上下文中出现的[Image](Image.zh-Hans.md) 和[Color](Color.zh-Hans.md) 等类型。您还可以为自己的目的访问存储在环境中的值。

## 绘制路径

- **stroke(_:with:lineWidth:)**：以指定的线宽在上下文中绘制路径。
- **stroke(_:with:style:)**：以指定的笔画样式在上下文中绘制路径。
- **fill(_:with:style:)**：在上下文中绘制路径并填充轮廓区域。
- **GraphicsContext.Shading**：用于勾画或填充路径的颜色或图案。
- **GraphicsContext.GradientOptions**：影响颜色渐变渲染的选项。

## 绘制图像、文本和视图

- **draw(_:in:)**：使用指定的矩形作为布局框架，在上下文中绘制已解析的符号。
- **draw(_:in:style:)**：使用指定的矩形作为布局框架，在上下文中绘制解析图像。
- **draw(_:at:anchor:)**：在上下文中绘制解析图像，将图像中的锚点与上下文中的点对齐。

## 绘制新图层

- **drawLayer(content:)**：在上下文中绘制由您提供的绘制代码创建的新图层。

## 解决绘制的实体

- **resolve(_:)**：获取与图形上下文环境的当前值固定的图像版本。
- **resolveSymbol(id:)**：如果存在已识别的子视图，则以已解析符号的形式获取该视图。
- **GraphicsContext.ResolvedSymbol**：可多次绘制的静态绘制操作序列，保留其分辨率独立性。
- **GraphicsContext.ResolvedImage**：根据特定环境解析的图像。
- **GraphicsContext.ResolvedText**：解析到特定环境的文本视图。

## 遮罩

- **clip(to:style:options:)**：将路径添加到上下文的剪辑形状数组中。
- **clipToLayer(opacity:options:content:)**：将您在新图层中定义的剪辑形状添加到上下文的剪辑形状数组中。
- **clipBoundingRect**：当前用户空间中所有当前剪辑形状交点的边界矩形。
- **GraphicsContext.ClipOptions**：影响剪贴图形使用的选项。

## 设置不透明度和混合模式

- **opacity**：上下文中绘图操作的不透明度。
- **blendMode**：上下文中绘图操作使用的混合模式。
- **GraphicsContext.BlendMode**：图形上下文将新内容与背景内容相结合的方式。

## 过滤

- **addFilter(_:options:)**：添加适用于后续绘图操作的过滤器。
- **GraphicsContext.Filter**：将图像处理操作应用于渲染内容的类型。
- **GraphicsContext.FilterOptions**：用于配置添加到图形上下文的过滤器的选项。
- **GraphicsContext.BlurOptions**：用于配置创建模糊的图形上下文过滤器的选项。
- **GraphicsContext.ShadowOptions**：配置创建阴影的图形上下文过滤器的选项。

## 应用变换

- **scaleBy(x:y:)**：在每个维度上按一定量缩放后续绘图操作。
- **rotate(by:)**：将后续绘图操作旋转一个角度。
- **translateBy(x:y:)**：将后续绘图操作在每个尺寸上移动一定量。
- **concatenate(_:)**：将给定的变换附加到上下文的现有变换中。
- **transform**：当前变换矩阵，定义用户空间坐标。

## 使用核心图形上下文绘制

- **withCGContext(content:)**：提供一个核心图形上下文，您可以用它作为代理，在此上下文中绘图。

## 访问环境

- **environment**：与图形上下文关联的环境。

### 实例方法

- **draw(_:options:)**：在图形上下文中绘制 `line`。

## 立即模式绘图

- 为你的 SwiftUI 应用程序添加丰富的图形**：通过添加背景材质、鲜艳度、自定义图形和动画，让您的应用程序脱颖而出。
- **Canvas**：支持即时模式绘图的视图类型。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext
crawled: 2025-12-02T16:15:44Z
---

# GraphicsContext

**Structure**

An immediate mode drawing destination, and its current state.

## Declaration

```swift
@frozen struct GraphicsContext
```

## Overview

Use a context to execute 2D drawing primitives. For example, you can draw filled shapes using the [fill(_:with:style:)](GraphicsContext/fill___with_style.zh-Hans.md) method inside a [Canvas](Canvas.zh-Hans.md) view:

```swift
Canvas { context, size in
    context.fill(
        Path(ellipseIn: CGRect(origin: .zero, size: size)),
        with: .color(.green))
}
.frame(width: 300, height: 200)
```

The example above draws an ellipse that just fits inside a canvas that’s constrained to 300 points wide and 200 points tall:



In addition to outlining or filling paths, you can draw images, text, and SwiftUI views. You can also use the context to perform many common graphical operations, like adding masks, applying filters and transforms, and setting a blend mode. For example you can add a mask using the [clip(to:style:options:)](GraphicsContext/clip_to_style_options.zh-Hans.md) method:

```swift
let halfSize = size.applying(CGAffineTransform(scaleX: 0.5, y: 0.5))
context.clip(to: Path(CGRect(origin: .zero, size: halfSize)))
context.fill(
    Path(ellipseIn: CGRect(origin: .zero, size: size)),
    with: .color(.green))
```

The rectangular mask hides all but one quadrant of the ellipse:



The order of operations matters. Changes that you make to the state of the context, like adding a mask or a filter, apply to later drawing operations. If you reverse the fill and clip operations in the example above, so that the fill comes first, the mask doesn’t affect the ellipse.

Each context references a particular layer in a tree of transparency layers, and also contains a full copy of the drawing state. You can modify the state of one context without affecting the state of any other, even if they refer to the same layer. For example you can draw the masked ellipse from the previous example into a copy of the main context, and then add a rectangle into the main context:

```swift
// Create a copy of the context to draw a clipped ellipse.
var maskedContext = context
let halfSize = size.applying(CGAffineTransform(scaleX: 0.5, y: 0.5))
maskedContext.clip(to: Path(CGRect(origin: .zero, size: halfSize)))
maskedContext.fill(
    Path(ellipseIn: CGRect(origin: .zero, size: size)),
    with: .color(.green))

// Go back to the original context to draw the rectangle.
let origin = CGPoint(x: size.width / 4, y: size.height / 4)
context.fill(
    Path(CGRect(origin: origin, size: halfSize)),
    with: .color(.blue))
```

The mask doesn’t clip the rectangle because the mask isn’t part of the main context. However, both contexts draw into the same view because you created one context as a copy of the other:



The context has access to an [EnvironmentValues](EnvironmentValues.zh-Hans.md) instance called [environment](GraphicsContext/environment.zh-Hans.md) that’s initially copied from the environment of its enclosing view. SwiftUI uses environment values — like the display resolution and color scheme — to resolve types like [Image](Image.zh-Hans.md) and [Color](Color.zh-Hans.md) that appear in the context. You can also access values stored in the environment for your own purposes.

## Drawing a path

- **stroke(_:with:lineWidth:)**: Draws a path into the context with a specified line width.
- **stroke(_:with:style:)**: Draws a path into the context with a specified stroke style.
- **fill(_:with:style:)**: Draws a path into the context and fills the outlined region.
- **GraphicsContext.Shading**: A color or pattern that you can use to outline or fill a path.
- **GraphicsContext.GradientOptions**: Options that affect the rendering of color gradients.

## Drawing images, text, and views

- **draw(_:in:)**: Draws a resolved symbol into the context, using the specified rectangle as a layout frame.
- **draw(_:in:style:)**: Draws a resolved image into the context, using the specified rectangle as a layout frame.
- **draw(_:at:anchor:)**: Draws a resolved image into the context, aligning an anchor within the image to a point in the context.

## Drawing into a new layer

- **drawLayer(content:)**: Draws a new layer, created by drawing code that you provide, into the context.

## Resolving a drawn entity

- **resolve(_:)**: Gets a version of an image that’s fixed with the current values of the graphics context’s environment.
- **resolveSymbol(id:)**: Gets the identified child view as a resolved symbol, if the view exists.
- **GraphicsContext.ResolvedSymbol**: A static sequence of drawing operations that may be drawn multiple times, preserving their resolution independence.
- **GraphicsContext.ResolvedImage**: An image resolved to a particular environment.
- **GraphicsContext.ResolvedText**: A text view resolved to a particular environment.

## Masking

- **clip(to:style:options:)**: Adds a path to the context’s array of clip shapes.
- **clipToLayer(opacity:options:content:)**: Adds a clip shape that you define in a new layer to the context’s array of clip shapes.
- **clipBoundingRect**: The bounding rectangle of the intersection of all current clip shapes in the current user space.
- **GraphicsContext.ClipOptions**: Options that affect the use of clip shapes.

## Setting opacity and the blend mode

- **opacity**: The opacity of drawing operations in the context.
- **blendMode**: The blend mode used by drawing operations in the context.
- **GraphicsContext.BlendMode**: The ways that a graphics context combines new content with background content.

## Filtering

- **addFilter(_:options:)**: Adds a filter that applies to subsequent drawing operations.
- **GraphicsContext.Filter**: A type that applies image processing operations to rendered content.
- **GraphicsContext.FilterOptions**: Options that configure a filter that you add to a graphics context.
- **GraphicsContext.BlurOptions**: Options that configure the graphics context filter that creates blur.
- **GraphicsContext.ShadowOptions**: Options that configure the graphics context filter that creates shadows.

## Applying transforms

- **scaleBy(x:y:)**: Scales subsequent drawing operations by an amount in each dimension.
- **rotate(by:)**: Rotates subsequent drawing operations by an angle.
- **translateBy(x:y:)**: Moves subsequent drawing operations by an amount in each dimension.
- **concatenate(_:)**: Appends the given transform to the context’s existing transform.
- **transform**: The current transform matrix, defining user space coordinates.

## Drawing with a core graphics context

- **withCGContext(content:)**: Provides a Core Graphics context that you can use as a proxy to draw into this context.

## Accessing the environment

- **environment**: The environment associated with the graphics context.

## Instance Methods

- **draw(_:options:)**: Draws `line` into the graphics context.

## Immediate mode drawing

- **Add rich graphics to your SwiftUI app**: Make your apps stand out by adding background materials, vibrancy, custom graphics, and animations.
- **Canvas**: A view type that supports immediate mode drawing.

