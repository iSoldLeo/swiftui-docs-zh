--- 来源：https://developer.apple.com/documentation/SwiftUI/ShapeStyle
抓取时间：2025-12-02T17:36:54Z

---

# ShapeStyle

**Protocol**

用于渲染形状的颜色或图案。

## 声明

```swift
protocol ShapeStyle : Sendable
```

## 概述

您可以通过声明一个符合 `ShapeStyle` 协议的类型，并实现所需的 `resolve` 函数来创建自定义形状样式。该函数会根据当前环境返回表示所需外观的形状样式。

例如，此形状样式会从环境中读取当前配色方案，以选择其颜色将与之合成的混合模式：

```swift
struct MyShapeStyle: ShapeStyle {
    func resolve(in environment: EnvironmentValues) -> some ShapeStyle {
        if environment.colorScheme == .light {
            return Color.red.blendMode(.lighten)
        } else {
            return Color.red.blendMode(.darken)
        }
    }
}
```

除了创建自定义形状样式外，您还可以使用 SwiftUI 定义的特定样式。要指定特定颜色或图案，您可以使用 [Color](Color.zh-Hans.md) 或 [image(_:sourceRect:scale:)](ShapeStyle/image___sourceRect_scale.zh-Hans.md) 返回的样式，或者使用渐变类型，例如 [radialGradient(_:center:startRadius:endRadius:)](ShapeStyle/radialGradient___center_startRadius_endRadius.zh-Hans.md) 返回的渐变类型。要设置适合特定平台特定上下文的颜色，请使用语义样式，例如 [background](ShapeStyle/background.zh-Hans.md) 或 [primary](ShapeStyle/primary.zh-Hans.md)。

您可以通过以下方式使用形状样式：

- 使用 [fill(_:style:)](Shape/fill___style.zh-Hans.md) 修饰符填充形状：

```swift
Path { path in
    path.move(to: .zero)
    path.addLine(to: CGPoint(x: 50, y: 0))
    path.addArc(
        center: .zero,
        radius: 50,
        startAngle: .zero,
        endAngle: .degrees(90),
        clockwise: false)
}
.fill(.radialGradient(
    Gradient(colors: [.yellow, .red]),
    center: .topLeading,
    startRadius: 15,
    endRadius: 80))
```

- 使用 [stroke(_:lineWidth:)](Shape/stroke___lineWidth.zh-Hans.md) 或 [stroke(_:style:)](Shape/stroke___style.zh-Hans.md) 修饰符勾勒形状轮廓：

```swift
RoundedRectangle(cornerRadius: 10)
    .stroke(.mint, lineWidth: 10)
    .frame(width: 200, height: 50)
```

- 使用 [foregroundStyle(_:)](View/foregroundStyle.zh-Hans.md) 修饰符设置视图中前景元素的样式：

```swift
VStack(alignment: .leading) {
    Text("Primary")
        .font(.title)
    Text("Secondary")
        .font(.caption)
        .foregroundStyle(.secondary)
}
```

## 系统颜色

- **black**：适用于 UI 元素的黑色。

- **blue**：适用于 UI 元素的上下文相关蓝色。

- **brown**：一种上下文相关的棕色，适用于用户界面元素。

- **clear**：一种透明色，适用于用户界面元素。

- **cyan**：一种上下文相关的青色，适用于用户界面元素。

- **gray**：一种上下文相关的灰色，适用于用户界面元素。

- **green**：一种上下文相关的绿色，适用于用户界面元素。

- **indigo**：一种上下文相关的靛蓝色，适用于用户界面元素。

- **mint**：一种上下文相关的薄荷绿色，适用于用户界面元素。

- **orange**：一种上下文相关的橙色，适用于用户界面元素。

- **pink**：适用于 UI 元素的上下文相关粉色。

- **purple**：适用于 UI 元素的上下文相关紫色。

- **red**：适用于 UI 元素的上下文相关红色。

- **teal**：适用于 UI 元素的上下文相关青色。

- **white**：适用于 UI 元素的白色。

- **yellow**：适用于 UI 元素的上下文相关黄色。

## 角度渐变

- **angularGradient(_:center:startAngle:endAngle:)**：角度渐变，颜色函数会随着起始角度和结束角度之间的角度变化而变化，并以填充形状内的相对中心点为锚点。

- **angularGradient(colors:center:startAngle:endAngle:)**：由一组颜色定义的角度渐变。

- **angularGradient(stops:center:startAngle:endAngle:)**：由一组颜色停止点定义的角度渐变。

## 圆锥渐变

- **conicGradient(_:center:angle:)**：完成完整旋转的圆锥渐变，可选择从给定角度开始，并锚定到填充形状内的相对中心点。

- **conicGradient(colors:center:angle:)**：由一组颜色定义并完成完整旋转的圆锥渐变。

- **conicGradient(stops:center:angle:)**：由一组颜色停止点定义并完成完整旋转的圆锥渐变。

## 椭圆渐变

- **ellipticalGradient(_:center:startRadiusFraction:endRadiusFraction:)**：绘制椭圆的径向渐变。

- **ellipticalGradient(colors:center:startRadiusFraction:endRadiusFraction:)**：径向渐变，绘制由一组颜色定义的椭圆。

- **ellipticalGradient(stops:center:startRadiusFraction:endRadiusFraction:)**：径向渐变，绘制由一组颜色停止点定义的椭圆。

## 线性渐变

- **linearGradient(_:startPoint:endPoint:)**：线性渐变。

- **linearGradient(colors:startPoint:endPoint:)**：线性渐变，由一组颜色定义。

- **linearGradient(stops:startPoint:endPoint:)**：线性渐变，由一组颜色停止点定义。

## 径向渐变

- **radialGradient(_:center:startRadius:endRadius:)**：径向渐变。

- **radialGradient(colors:center:startRadius:endRadius:)**：径向渐变，由一组颜色定义。

- **radialGradient(stops:center:startRadius:endRadius:)**：径向渐变，由一组颜色停止点定义。

## 材质

- **ultraThinMaterial**：半透明材质。

- **thinMaterial**：半透明材质。

- **regularMaterial**：半透明材质。

- **thickMaterial**：不透明材质。

- **ultraThickMaterial**：半透明材质。

- **bar**：与系统工具栏样式相匹配的材质。

## 图像绘制样式

- **image(_:sourceRect:scale:)**：通过重复图像区域来填充形状的形状样式。

## 层级样式

- **secondary**：返回此形状样式的第二层级。

- **tertiary**：返回此形状样式的第三级。

- **quaternary**：返回此形状样式的第四级。

- **quinary**：返回此形状样式的第五级。

- **primary**：映射到当前内容样式第一级的形状样式。

- **secondary**：映射到当前内容样式第二级的形状样式。

- **tertiary**：映射到当前内容样式第三级的形状样式。

- **quaternary**：映射到当前内容样式第四级的形状样式。

- **quinary**：映射到当前内容样式第五级的形状样式。

## 语义样式

- **foreground**：当前上下文中的前景色样式。

- **background**：当前上下文中的背景色样式。

- **selection**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **separator**：适用于前景色分隔线或边框线的样式。

- **tint**：反映当前色调颜色的样式。

- **placeholder**：适用于占位符文本的样式。

- **link**：适用于链接的样式。

- **fill**：用于填充形状的叠加填充样式。

- **windowBackground**：适用于应与包含窗口背景相匹配的元素的样式。

## 修改形状样式

- **blendMode(_:)**：返回基于 `self` 的新样式，该样式在绘制时应用指定的混合模式。

- **opacity(_:)**：返回基于 `self` 的新样式，该样式在绘制时乘以指定的透明度。

- **shadow(_:)**：将指定的阴影效果应用于形状样式。

## 配置默认形状样式

- **blendMode(_:)**：返回基于当前样式的新样式，该样式在绘制时使用 `mode` 作为其混合模式。

- **opacity(_:)**：返回一个基于当前样式的新样式，绘制时乘以 `opacity`。

- **shadow(_:)**：返回一个形状样式，该样式将指定的阴影样式应用于当前样式。

## 映射到绝对坐标

- **in(_:)**：将形状样式的单位空间坐标映射到给定矩形的绝对坐标。

## 在环境中解析形状样式

- **resolve(in:)**：根据当前的 `environment` 计算已解析的形状样式。

- **Resolved**：此形状样式将解析为的类型。

## 将形状样式用作视图

- **body**：填充了形状样式的矩形视图。

## 支持的类型

- **AngularGradient**：角度渐变。

- **EllipticalGradient**：绘制椭圆的径向渐变。

- **LinearGradient**：线性渐变。

- **RadialGradient**：径向渐变。

- **Material**：背景材质类型。

- **ImagePaint**：通过重复图像区域来填充形状的形状样式。

- **HierarchicalShapeStyle**：映射到编号内容样式之一的形状样式。

- **HierarchicalShapeStyleModifier**：可应用于层级形状的样式。

- **ForegroundStyle**：当前上下文中的前景色样式。

- **BackgroundStyle**：当前上下文中的背景色样式。

- **SelectionShapeStyle**：用于根据平台常规颜色和行为以视觉方式指示选中状态的样式。

- **SeparatorShapeStyle**：适用于前景色分隔符或边框线的样式。

- **TintShapeStyle**：反映当前色调颜色的样式。

- **FillShapeStyle**：显示叠加填充之一的形状样式。

- **LinkShapeStyle**：适用于链接的样式。

- **PlaceholderTextShapeStyle**：适用于占位符文本的样式。

- **WindowBackgroundShapeStyle**：适用于应与其容器窗口背景相匹配的元素的样式。

## 实例方法

- **materialActiveAppearance(_:)**：为使用此样式创建的材质设置显式活动外观。

## 内容样式

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。

- **foregroundStyle(_:)**：设置视图的前景色元素使用给定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景色样式的一级和二级样式。

- **foregroundStyle(_:_:_:)**：设置前景色样式的一级、二级和三级样式。

- **backgroundStyle(_:)**：设置用于渲染视图背景的指定样式。

- **backgroundStyle**：可选样式，设置后会覆盖默认的系统背景样式。

- **AnyShapeStyle**：已擦除类型的 ShapeStyle 值。

- **Gradient**：颜色渐变，表示为颜色停止点数组，每个停止点都有一个参数化的位置值。

- **MeshGradient**：由定位颜色的二维网格定义的二维渐变。

- **AnyGradient**：颜色渐变。

- **ShadowStyle**：用于渲染阴影的样式。

- **Glass**：定义液态玻璃材质配置的结构。

## 继承自

- Sendable

- SendableMetatype

## 符合的类型

- AngularGradient

- AnyGradient

- AnyShapeStyle

- BackgroundStyle

- Color

- Color.Resolved

- Color.ResolvedHDR

- EllipticalGradient

- FillShapeStyle

- ForegroundStyle

- Gradient
- HierarchicalShapeStyle

- HierarchicalShapeStyleModifier

- ImagePaint

- LinearGradient

- LinkShapeStyle

- Material
- MeshGradient

- PlaceholderTextShapeStyle

- RadialGradient

- SelectionShapeStyle

- SeparatorShapeStyle

- Shader

- TintShapeStyle

- WindowBackgroundShapeStyle


---
source: https://developer.apple.com/documentation/SwiftUI/ShapeStyle
crawled: 2025-12-02T17:36:54Z
---

# ShapeStyle

**Protocol**

A color or pattern to use when rendering a shape.

## Declaration

```swift
protocol ShapeStyle : Sendable
```

## Overview

You create custom shape styles by declaring a type that conforms to the `ShapeStyle` protocol and implementing the required `resolve` function to return a shape style that represents the desired appearance based on the current environment.

For example this shape style reads the current color scheme from the environment to choose the blend mode its color will be composited with:

```swift
struct MyShapeStyle: ShapeStyle {
    func resolve(in environment: EnvironmentValues) -> some ShapeStyle {
        if environment.colorScheme == .light {
            return Color.red.blendMode(.lighten)
        } else {
            return Color.red.blendMode(.darken)
        }
    }
}
```

In addition to creating a custom shape style, you can also use one of the concrete styles that SwiftUI defines. To indicate a specific color or pattern, you can use [Color](Color.zh-Hans.md) or the style returned by [image(_:sourceRect:scale:)](ShapeStyle/image___sourceRect_scale.zh-Hans.md), or one of the gradient types, like the one returned by [radialGradient(_:center:startRadius:endRadius:)](ShapeStyle/radialGradient___center_startRadius_endRadius.zh-Hans.md). To set a color that’s appropriate for a given context on a given platform, use one of the semantic styles, like [background](ShapeStyle/background.zh-Hans.md) or [primary](ShapeStyle/primary.zh-Hans.md).

You can use a shape style by:

- Filling a shape with a style with the [fill(_:style:)](Shape/fill___style.zh-Hans.md) modifier:

```swift
Path { path in
    path.move(to: .zero)
    path.addLine(to: CGPoint(x: 50, y: 0))
    path.addArc(
        center: .zero,
        radius: 50,
        startAngle: .zero,
        endAngle: .degrees(90),
        clockwise: false)
}
.fill(.radialGradient(
    Gradient(colors: [.yellow, .red]),
    center: .topLeading,
    startRadius: 15,
    endRadius: 80))
```


- Tracing the outline of a shape with a style with either the [stroke(_:lineWidth:)](Shape/stroke___lineWidth.zh-Hans.md) or the [stroke(_:style:)](Shape/stroke___style.zh-Hans.md) modifier:

```swift
RoundedRectangle(cornerRadius: 10)
    .stroke(.mint, lineWidth: 10)
    .frame(width: 200, height: 50)
```


- Styling the foreground elements in a view with the [foregroundStyle(_:)](View/foregroundStyle.zh-Hans.md) modifier:

```swift
VStack(alignment: .leading) {
    Text("Primary")
        .font(.title)
    Text("Secondary")
        .font(.caption)
        .foregroundStyle(.secondary)
}
```



## System colors

- **black**: A black color suitable for use in UI elements.
- **blue**: A context-dependent blue color suitable for use in UI elements.
- **brown**: A context-dependent brown color suitable for use in UI elements.
- **clear**: A clear color suitable for use in UI elements.
- **cyan**: A context-dependent cyan color suitable for use in UI elements.
- **gray**: A context-dependent gray color suitable for use in UI elements.
- **green**: A context-dependent green color suitable for use in UI elements.
- **indigo**: A context-dependent indigo color suitable for use in UI elements.
- **mint**: A context-dependent mint color suitable for use in UI elements.
- **orange**: A context-dependent orange color suitable for use in UI elements.
- **pink**: A context-dependent pink color suitable for use in UI elements.
- **purple**: A context-dependent purple color suitable for use in UI elements.
- **red**: A context-dependent red color suitable for use in UI elements.
- **teal**: A context-dependent teal color suitable for use in UI elements.
- **white**: A white color suitable for use in UI elements.
- **yellow**: A context-dependent yellow color suitable for use in UI elements.

## Angular gradients

- **angularGradient(_:center:startAngle:endAngle:)**: An angular gradient, which applies the color function as the angle changes between the start and end angles, and anchored to a relative center point within the filled shape.
- **angularGradient(colors:center:startAngle:endAngle:)**: An angular gradient defined by a collection of colors.
- **angularGradient(stops:center:startAngle:endAngle:)**: An angular gradient defined by a collection of color stops.

## Conic gradients

- **conicGradient(_:center:angle:)**: A conic gradient that completes a full turn, optionally starting from a given angle and anchored to a relative center point within the filled shape.
- **conicGradient(colors:center:angle:)**: A conic gradient defined by a collection of colors that completes a full turn.
- **conicGradient(stops:center:angle:)**: A conic gradient defined by a collection of color stops that completes a full turn.

## Elliptical gradients

- **ellipticalGradient(_:center:startRadiusFraction:endRadiusFraction:)**: A radial gradient that draws an ellipse.
- **ellipticalGradient(colors:center:startRadiusFraction:endRadiusFraction:)**: A radial gradient that draws an ellipse defined by a collection of colors.
- **ellipticalGradient(stops:center:startRadiusFraction:endRadiusFraction:)**: A radial gradient that draws an ellipse defined by a collection of color stops.

## Linear gradients

- **linearGradient(_:startPoint:endPoint:)**: A linear gradient.
- **linearGradient(colors:startPoint:endPoint:)**: A linear gradient defined by a collection of colors.
- **linearGradient(stops:startPoint:endPoint:)**: A linear gradient defined by a collection of color stops.

## Radial gradients

- **radialGradient(_:center:startRadius:endRadius:)**: A radial gradient.
- **radialGradient(colors:center:startRadius:endRadius:)**: A radial gradient defined by a collection of colors.
- **radialGradient(stops:center:startRadius:endRadius:)**: A radial gradient defined by a collection of color stops.

## Materials

- **ultraThinMaterial**: A mostly translucent material.
- **thinMaterial**: A material that’s more translucent than opaque.
- **regularMaterial**: A material that’s somewhat translucent.
- **thickMaterial**: A material that’s more opaque than translucent.
- **ultraThickMaterial**: A mostly opaque material.
- **bar**: A material matching the style of system toolbars.

## Image paint styles

- **image(_:sourceRect:scale:)**: A shape style that fills a shape by repeating a region of an image.

## Hierarchical styles

- **secondary**: Returns the second level of this shape style.
- **tertiary**: Returns the third level of this shape style.
- **quaternary**: Returns the fourth level of this shape style.
- **quinary**: Returns the fifth level of this shape style.
- **primary**: A shape style that maps to the first level of the current content style.
- **secondary**: A shape style that maps to the second level of the current content style.
- **tertiary**: A shape style that maps to the third level of the current content style.
- **quaternary**: A shape style that maps to the fourth level of the current content style.
- **quinary**: A shape style that maps to the fifth level of the current content style.

## Semantic styles

- **foreground**: The foreground style in the current context.
- **background**: The background style in the current context.
- **selection**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **separator**: A style appropriate for foreground separator or border lines.
- **tint**: A style that reflects the current tint color.
- **placeholder**: A style appropriate for placeholder text.
- **link**: A style appropriate for links.
- **fill**: An overlay fill style for filling shapes.
- **windowBackground**: A style appropriate for elements that should match the background of their containing window.

## Modifying a shape style

- **blendMode(_:)**: Returns a new style based on `self` that applies the specified blend mode when drawing.
- **opacity(_:)**: Returns a new style based on `self` that multiplies by the specified opacity when drawing.
- **shadow(_:)**: Applies the specified shadow effect to the shape style.

## Configuring the default shape style

- **blendMode(_:)**: Returns a new style based on the current style that uses `mode` as its blend mode when drawing.
- **opacity(_:)**: Returns a new style based on the current style that multiplies by `opacity` when drawing.
- **shadow(_:)**: Returns a shape style that applies the specified shadow style to the current style.

## Mapping to absolute coordinates

- **in(_:)**: Maps a shape style’s unit-space coordinates to the absolute coordinates of a given rectangle.

## Resolving a shape style in an environment

- **resolve(in:)**: Evaluate to a resolved shape style given the current `environment`.
- **Resolved**: The type of shape style this will resolve to.

## Using a shape style as a view

- **body**: A rectangular view that’s filled with the shape style.

## Supporting types

- **AngularGradient**: An angular gradient.
- **EllipticalGradient**: A radial gradient that draws an ellipse.
- **LinearGradient**: A linear gradient.
- **RadialGradient**: A radial gradient.
- **Material**: A background material type.
- **ImagePaint**: A shape style that fills a shape by repeating a region of an image.
- **HierarchicalShapeStyle**: A shape style that maps to one of the numbered content styles.
- **HierarchicalShapeStyleModifier**: Styles that you can apply to hierarchical shapes.
- **ForegroundStyle**: The foreground style in the current context.
- **BackgroundStyle**: The background style in the current context.
- **SelectionShapeStyle**: A style used to visually indicate selection following platform conventional colors and behaviors.
- **SeparatorShapeStyle**: A style appropriate for foreground separator or border lines.
- **TintShapeStyle**: A style that reflects the current tint color.
- **FillShapeStyle**: A shape style that displays one of the overlay fills.
- **LinkShapeStyle**: A style appropriate for links.
- **PlaceholderTextShapeStyle**: A style appropriate for placeholder text.
- **WindowBackgroundShapeStyle**: A style appropriate for elements that should match the background of their containing window.

## Instance Methods

- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials created by this style.

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **AnyShapeStyle**: A type-erased ShapeStyle value.
- **Gradient**: A color gradient represented as an array of color stops, each having a parametric location value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **AnyGradient**: A color gradient.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

## Inherits From

- Sendable
- SendableMetatype

## Conforming Types

- AngularGradient
- AnyGradient
- AnyShapeStyle
- BackgroundStyle
- Color
- Color.Resolved
- Color.ResolvedHDR
- EllipticalGradient
- FillShapeStyle
- ForegroundStyle
- Gradient
- HierarchicalShapeStyle
- HierarchicalShapeStyleModifier
- ImagePaint
- LinearGradient
- LinkShapeStyle
- Material
- MeshGradient
- PlaceholderTextShapeStyle
- RadialGradient
- SelectionShapeStyle
- SeparatorShapeStyle
- Shader
- TintShapeStyle
- WindowBackgroundShapeStyle

