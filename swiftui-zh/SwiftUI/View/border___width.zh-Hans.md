--- 来源：https://developer.apple.com/documentation/SwiftUI/View/border(_:width:)

抓取时间：2025-11-30T21:21:53Z

---

# border(_:width:)

**实例方法**

为该视图添加指定样式和宽度的边框。

## 声明

```swift
nonisolated func border<S>(_ content: S, width: CGFloat = 1) -> some View where S : ShapeStyle

```

## 参数

- **content**：符合 [ShapeStyle](../ShapeStyle.zh-Hans.md) 协议的值，例如 [Color](../Color.zh-Hans.md) 或 [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md)，SwiftUI 使用该值填充边框。

- **width**：边框的粗细。默认值为 1 像素。

## 返回值

为当前视图添加指定样式和宽度的边框。

## 说明

使用此修饰符可在视图的框架周围绘制指定宽度的边框。默认情况下，边框位于视图边界内。例如，您可以添加一个 4 磅宽的边框来覆盖文本：

```swift
Text("Purple border inside the view bounds.")
    .border(Color.purple, width: 4)
```

要在视图外部添加边框，请在添加边框之前应用相同宽度的内边距：

```swift
Text("Purple border outside the view bounds.")
    .padding(4)
    .border(Color.purple, width: 4)
```

## 设置内容样式

- **foregroundStyle(_:)**：设置视图的前景色元素使用给定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景色样式的主要和次要级别。

- **foregroundStyle(_:_:_:)**：设置前景色样式的主要、次要和三级。

- **backgroundStyle(_:)**：设置视图中背景的渲染样式。

- **backgroundStyle**：可选样式，设置后会覆盖默认的系统背景样式。

- **ShapeStyle**：用于渲染形状的颜色或图案。

- **AnyShapeStyle**：已擦除类型的 ShapeStyle 值。

- **Gradient**：颜色渐变，表示为颜色停止点数组，每个停止点都有一个参数化的位置值。

- **MeshGradient**：由定位颜色的二维网格定义的二维渐变。

- **AnyGradient**：颜色渐变。

- **ShadowStyle**：用于渲染阴影的样式。

- **Glass**：定义液态玻璃材料结构的结构。


---
source: https://developer.apple.com/documentation/SwiftUI/View/border(_:width:)
crawled: 2025-11-30T21:21:53Z
---

# border(_:width:)

**Instance Method**

Adds a border to this view with the specified style and width.

## Declaration

```swift
nonisolated func border<S>(_ content: S, width: CGFloat = 1) -> some View where S : ShapeStyle

```

## Parameters

- **content**: A value that conforms to the [ShapeStyle](../ShapeStyle.zh-Hans.md) protocol, like a [Color](../Color.zh-Hans.md) or [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md), that SwiftUI uses to fill the border.
- **width**: The thickness of the border. The default is 1 pixel.

## Return Value

A view that adds a border with the specified style and width to this view.

## Discussion

Use this modifier to draw a border of a specified width around the view’s frame. By default, the border appears inside the bounds of this view. For example, you can add a four-point wide border covers the text:

```swift
Text("Purple border inside the view bounds.")
    .border(Color.purple, width: 4)
```



To place a border around the outside of this view, apply padding of the same width before adding the border:

```swift
Text("Purple border outside the view bounds.")
    .padding(4)
    .border(Color.purple, width: 4)
```



## Styling content

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

