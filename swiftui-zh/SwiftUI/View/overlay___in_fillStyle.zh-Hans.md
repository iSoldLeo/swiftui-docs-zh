--- 来源：https://developer.apple.com/documentation/SwiftUI/View/overlay(_:in:fillStyle:)

抓取时间：2025-11-30T21:23:24Z

---

# overlay(_:in:fillStyle:)

**实例方法**

将您指定的形状叠加到此视图的前面。

## 声明

```swift
nonisolated func overlay<S, T>(_ style: S, in shape: T, fillStyle: FillStyle = FillStyle()) -> some View where S : ShapeStyle, T : Shape

```

## 参数

- **style**：SwiftUI 用于填充您指定形状的 [ShapeStyle](../ShapeStyle.zh-Hans.md) 对象。

- **shape**：符合 [Shape](../Shape.zh-Hans.md) 类型的实例，SwiftUI 将其绘制在视图前面。

- **fillStyle**：绘制形状时使用的 [FillStyle](../FillStyle.zh-Hans.md)。默认样式使用非零绕数规则和抗锯齿。

## 返回值

一个视图，其前面绘制了指定的形状。

## 说明

使用此修饰符可以将符合 [Shape](../Shape.zh-Hans.md) 协议的类型（例如 [Rectangle](../Rectangle.zh-Hans.md)、[Circle](../Circle.zh-Hans.md) 或 [Capsule](../Capsule.zh-Hans.md)）叠加在视图前面。指定一个用于填充形状的 [ShapeStyle](../ShapeStyle.zh-Hans.md)。例如，您可以将一个矩形的轮廓叠加在另一个矩形的前面：

```swift
Rectangle()
    .frame(width: 200, height: 100)
    .overlay(.teal, in: Rectangle().inset(by: 10).stroke(lineWidth: 5))
```

上面的示例使用 [inset(by:)](../InsettableShape/inset_by.zh-Hans.md) 方法略微缩小叠加矩形的尺寸，并使用 [stroke(lineWidth:)](../Shape/stroke_lineWidth.zh-Hans.md) 方法仅填充形状的轮廓。这将创建一个内嵌边框：

此修改器是一种便捷的方法，用于将形状叠加在视图之上。要处理更一般的情况，例如叠加 [View](../View.zh-Hans.md)（或视图堆栈），并控制其位置，请改用 [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md)。要使用 [ShapeStyle](../ShapeStyle.zh-Hans.md) 覆盖视图，请使用 [overlay(_:ignoresSafeAreaEdges:)](overlay___ignoresSafeAreaEdges.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后面创建背景，并将其扩展到安全区域内嵌范围之外。

- **ZStack**：一个覆盖其子视图的视图，并沿两个轴对齐。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的下方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图之前。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图之前。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置外层容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/overlay(_:in:fillStyle:)
crawled: 2025-11-30T21:23:24Z
---

# overlay(_:in:fillStyle:)

**Instance Method**

Layers a shape that you specify in front of this view.

## Declaration

```swift
nonisolated func overlay<S, T>(_ style: S, in shape: T, fillStyle: FillStyle = FillStyle()) -> some View where S : ShapeStyle, T : Shape

```

## Parameters

- **style**: A [ShapeStyle](../ShapeStyle.zh-Hans.md) that SwiftUI uses to fill the shape that you specify.
- **shape**: An instance of a type that conforms to [Shape](../Shape.zh-Hans.md) that SwiftUI draws in front of the view.
- **fillStyle**: The [FillStyle](../FillStyle.zh-Hans.md) to use when drawing the shape. The default style uses the nonzero winding number rule and antialiasing.

## Return Value

A view with the specified shape drawn in front of it.

## Discussion

Use this modifier to layer a type that conforms to the [Shape](../Shape.zh-Hans.md) protocol — like a [Rectangle](../Rectangle.zh-Hans.md), [Circle](../Circle.zh-Hans.md), or [Capsule](../Capsule.zh-Hans.md) — in front of a view. Specify a [ShapeStyle](../ShapeStyle.zh-Hans.md) that’s used to fill the shape. For example, you can overlay the outline of one rectangle in front of another:

```swift
Rectangle()
    .frame(width: 200, height: 100)
    .overlay(.teal, in: Rectangle().inset(by: 10).stroke(lineWidth: 5))
```

The example above uses the [inset(by:)](../InsettableShape/inset_by.zh-Hans.md) method to slightly reduce the size of the overlaid rectangle, and the [stroke(lineWidth:)](../Shape/stroke_lineWidth.zh-Hans.md) method to fill only the shape’s outline. This creates an inset border:



This modifier is a convenience method for layering a shape over a view. To handle the more general case of overlaying a [View](../View.zh-Hans.md) — or a stack of views — with control over the position, use [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md) instead. To cover a view with a [ShapeStyle](../ShapeStyle.zh-Hans.md), use [overlay(_:ignoresSafeAreaEdges:)](overlay___ignoresSafeAreaEdges.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

