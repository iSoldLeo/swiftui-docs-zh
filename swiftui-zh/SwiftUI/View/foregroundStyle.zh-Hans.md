--- 来源：https://developer.apple.com/documentation/SwiftUI/View/foregroundStyle(_:_:_:)

抓取时间：2025-11-30T21:21:56Z

---

# foregroundStyle(_:_:_:)

**实例方法**

设置前景样式的主色、次色和三级颜色。

## 声明

```swift
nonisolated func foregroundStyle<S1, S2, S3>(_ primary: S1, _ secondary: S2, _ tertiary: S3) -> some View where S1 : ShapeStyle, S2 : ShapeStyle, S3 : ShapeStyle

```

## 参数

- **primary**：用于填充前景元素的主色或图案。要指定特定值，请使用 [Color](../Color.zh-Hans.md) 或 [image(_:sourceRect:scale:)](../ShapeStyle/image___sourceRect_scale.zh-Hans.md)，或者使用渐变类型，例如 [linearGradient(colors:startPoint:endPoint:)](../ShapeStyle/linearGradient_colors_startPoint_endPoint.zh-Hans.md)。要设置与包含视图样式相关的样式，请使用语义样式，例如 [primary](../ShapeStyle/primary.zh-Hans.md)。

- **secondary**：用于填充前景元素的辅助颜色或图案。

- **tertiary**：用于填充前景元素的第三颜色或图案。

## 返回值

使用给定前景样式的视图。

## 说明

SwiftUI 在渲染没有显式渲染样式的子视图（例如图像、文本、形状等）时使用这些样式。

如果您没有显式指定其他模式，则应用此修饰符时，视图层次结构中的符号图像将使用 [palette](../SymbolRenderingMode/palette.zh-Hans.md) 渲染模式。

## 样式设置

- **border(_:width:)**：为该视图添加指定样式和宽度的边框。

- **foregroundStyle(_:)**：设置视图的前景色元素使用给定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景色样式的主级别和次级别。

- **backgroundStyle(_:)**：设置指定的样式以渲染视图中的背景。

- **backgroundStyle**：可选样式，设置后会覆盖默认的系统背景样式。

- **ShapeStyle**：渲染形状时使用的颜色或图案。

- **AnyShapeStyle**：已删除文本的 ShapeStyle 值。

- **Gradient**：一个颜色渐变，以颜色停止点数组的形式表示，每个停止点都有一个参数化的位置值。

- **MeshGradient**：一个二维渐变，由一个二维网格中定位的颜色定义。

- **AnyGradient**：一个颜色渐变。

- **ShadowStyle**：一种用于渲染阴影的样式。

- **Glass**：一个定义液态玻璃材质配置的结构体。


---
source: https://developer.apple.com/documentation/SwiftUI/View/foregroundStyle(_:_:_:)
crawled: 2025-11-30T21:21:56Z
---

# foregroundStyle(_:_:_:)

**Instance Method**

Sets the primary, secondary, and tertiary levels of the foreground style.

## Declaration

```swift
nonisolated func foregroundStyle<S1, S2, S3>(_ primary: S1, _ secondary: S2, _ tertiary: S3) -> some View where S1 : ShapeStyle, S2 : ShapeStyle, S3 : ShapeStyle

```

## Parameters

- **primary**: The primary color or pattern to use when filling in the foreground elements. To indicate a specific value, use [Color](../Color.zh-Hans.md) or [image(_:sourceRect:scale:)](../ShapeStyle/image___sourceRect_scale.zh-Hans.md), or one of the gradient types, like [linearGradient(colors:startPoint:endPoint:)](../ShapeStyle/linearGradient_colors_startPoint_endPoint.zh-Hans.md). To set a style that’s relative to the containing view’s style, use one of the semantic styles, like [primary](../ShapeStyle/primary.zh-Hans.md).
- **secondary**: The secondary color or pattern to use when filling in the foreground elements.
- **tertiary**: The tertiary color or pattern to use when filling in the foreground elements.

## Return Value

A view that uses the given foreground styles.

## Discussion

SwiftUI uses these styles when rendering child views that don’t have an explicit rendering style, like images, text, shapes, and so on.

Symbol images within the view hierarchy use the [palette](../SymbolRenderingMode/palette.zh-Hans.md) rendering mode when you apply this modifier, if you don’t explicitly specify another mode.

## Styling content

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **backgroundStyle**: An optional style that overrides the default system background style when set.
- **ShapeStyle**: A color or pattern to use when rendering a shape.
- **AnyShapeStyle**: A type-erased ShapeStyle value.
- **Gradient**: A color gradient represented as an array of color stops, each having a parametric location value.
- **MeshGradient**: A two-dimensional gradient defined by a 2D grid of positioned colors.
- **AnyGradient**: A color gradient.
- **ShadowStyle**: A style to use when rendering shadows.
- **Glass**: A structure that defines the configuration of the Liquid Glass material.

