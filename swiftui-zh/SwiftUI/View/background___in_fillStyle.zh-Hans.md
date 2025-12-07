--- 来源：https://developer.apple.com/documentation/SwiftUI/View/background(_:in:fillStyle:)

抓取时间：2025-12-02T17:38:16Z

---

# background(_:in:fillStyle:)

**实例方法**

将视图的背景设置为一个可插入的形状，并填充指定样式。

## 声明

```swift
nonisolated func background<S, T>(_ style: S, in shape: T, fillStyle: FillStyle = FillStyle()) -> some View where S : ShapeStyle, T : InsettableShape

```

## 参数

- **style**：SwiftUI 用于填充指定形状的 [ShapeStyle](../ShapeStyle.zh-Hans.md) 类型。

- **shape**：SwiftUI 在视图后绘制的符合 [InsettableShape](../InsettableShape.zh-Hans.md) 类型的实例。

- **fillStyle**：绘制形状时使用的 [FillStyle](../FillStyle.zh-Hans.md)。默认样式使用非零绕数规则和抗锯齿。

## 返回值

一个视图，其后绘制有指定的可插入形状。

## 说明

使用此修饰符将符合 [InsettableShape](../InsettableShape.zh-Hans.md) 协议的类型（例如 [Rectangle](../Rectangle.zh-Hans.md)、[Circle](../Circle.zh-Hans.md) 或 [Capsule](../Capsule.zh-Hans.md)）置于视图后方。指定用于填充形状的 [ShapeStyle](../ShapeStyle.zh-Hans.md)。例如，您可以将 [RoundedRectangle](../RoundedRectangle.zh-Hans.md) 放置在 [Label](../Label.zh-Hans.md) 的后面：

```swift
Label("Flag", systemImage: "flag.fill")
    .padding()
    .background(.teal, in: RoundedRectangle(cornerRadius: 8))
```

[teal](../ShapeStyle/teal.zh-Hans.md) 颜色填充形状：

此修饰符是一种便捷方法，用于将单个形状放置在视图后面。要使用其他 [View](../View.zh-Hans.md) 类型（或视图堆栈）创建背景，请改用 [background(alignment:content:)](background_alignment_content.zh-Hans.md)。要将 [ShapeStyle](../ShapeStyle.zh-Hans.md) 添加为背景，请使用 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后面创建背景，并将其扩展到安全区域之外。

- **ZStack**：覆盖其子视图的视图，并在两个轴上对齐它们。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的下方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(in:fillStyle:)**：将视图的背景设置为填充了默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图置于此视图的前方。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式置于此视图的前方。

- **overlay(_:in:fillStyle:)**：将您指定的形状置于此视图的前方。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：设置视图的容器背景。

- **containerBackground(for:alignment:content:)**：设置视图的容器背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/background(_:in:fillStyle:)
crawled: 2025-12-02T17:38:16Z
---

# background(_:in:fillStyle:)

**Instance Method**

Sets the view’s background to an insettable shape filled with a style.

## Declaration

```swift
nonisolated func background<S, T>(_ style: S, in shape: T, fillStyle: FillStyle = FillStyle()) -> some View where S : ShapeStyle, T : InsettableShape

```

## Parameters

- **style**: A [ShapeStyle](../ShapeStyle.zh-Hans.md) that SwiftUI uses to the fill the shape that you specify.
- **shape**: An instance of a type that conforms to [InsettableShape](../InsettableShape.zh-Hans.md) that SwiftUI draws behind the view.
- **fillStyle**: The [FillStyle](../FillStyle.zh-Hans.md) to use when drawing the shape. The default style uses the nonzero winding number rule and antialiasing.

## Return Value

A view with the specified insettable shape drawn behind it.

## Discussion

Use this modifier to layer a type that conforms to the [InsettableShape](../InsettableShape.zh-Hans.md) protocol — like a [Rectangle](../Rectangle.zh-Hans.md), [Circle](../Circle.zh-Hans.md), or [Capsule](../Capsule.zh-Hans.md) — behind a view. Specify the [ShapeStyle](../ShapeStyle.zh-Hans.md) that’s used to fill the shape. For example, you can place a [RoundedRectangle](../RoundedRectangle.zh-Hans.md) behind a [Label](../Label.zh-Hans.md):

```swift
Label("Flag", systemImage: "flag.fill")
    .padding()
    .background(.teal, in: RoundedRectangle(cornerRadius: 8))
```

The [teal](../ShapeStyle/teal.zh-Hans.md) color fills the shape:



This modifier is a convenience method for placing a single shape behind a view. To create a background with other [View](../View.zh-Hans.md) types — or with a stack of views — use [background(alignment:content:)](background_alignment_content.zh-Hans.md) instead. To add a [ShapeStyle](../ShapeStyle.zh-Hans.md) as a background, use [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

