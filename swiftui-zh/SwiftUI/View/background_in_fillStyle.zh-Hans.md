--- 来源：https://developer.apple.com/documentation/SwiftUI/View/background(in:fillStyle:)

抓取时间：2025-11-30T21:23:21Z

---

# background(in:fillStyle:)

**实例方法**

将视图的背景设置为一个可插入的形状，并填充默认的背景样式。

## 声明

```swift
nonisolated func background<S>(in shape: S, fillStyle: FillStyle = FillStyle()) -> some View where S : InsettableShape

```

## 参数

- **shape**：符合 [InsettableShape](../InsettableShape.zh-Hans.md) 类型的实例，SwiftUI 会使用 [background](../ShapeStyle/background.zh-Hans.md) 形状样式将其绘制在视图后面。

- **fillStyle**：绘制形状时要使用的 [FillStyle](../FillStyle.zh-Hans.md)。默认样式使用非零绕数规则和抗锯齿。

## 返回值

一个视图，其后绘制有指定的可插入形状。

## 说明

此修饰符的行为类似于 [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md)，但它始终使用 [background](../ShapeStyle/background.zh-Hans.md) 形状样式来填充指定的可插入形状。例如，您可以将 [RoundedRectangle](../RoundedRectangle.zh-Hans.md) 用作 [Label](../Label.zh-Hans.md) 的背景：

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(in: RoundedRectangle(cornerRadius: 8))
}
```

如果没有背景修饰符，填充颜色会透过标签显示出来。使用此修饰符，标签的文本和图标将显示在一个填充了适合浅色或深色外观的颜色的形状背景上：

要使用其他 [View](../View.zh-Hans.md) 类型（或视图堆栈）创建背景，请改用 [background(alignment:content:)](background_alignment_content.zh-Hans.md)。要添加 [ShapeStyle](../ShapeStyle.zh-Hans.md) 作为背景，请使用 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：一个覆盖其子视图的视图，使它们在两个轴上对齐。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图分层到此视图的后面。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充了样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图的前面。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置包含容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置包含容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/background(in:fillStyle:)
crawled: 2025-11-30T21:23:21Z
---

# background(in:fillStyle:)

**Instance Method**

Sets the view’s background to an insettable shape filled with the default background style.

## Declaration

```swift
nonisolated func background<S>(in shape: S, fillStyle: FillStyle = FillStyle()) -> some View where S : InsettableShape

```

## Parameters

- **shape**: An instance of a type that conforms to [InsettableShape](../InsettableShape.zh-Hans.md) that SwiftUI draws behind the view using the [background](../ShapeStyle/background.zh-Hans.md) shape style.
- **fillStyle**: The [FillStyle](../FillStyle.zh-Hans.md) to use when drawing the shape. The default style uses the nonzero winding number rule and antialiasing.

## Return Value

A view with the specified insettable shape drawn behind it.

## Discussion

This modifier behaves like [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md), except that it always uses the [background](../ShapeStyle/background.zh-Hans.md) shape style to fill the specified insettable shape. For example, you can use a [RoundedRectangle](../RoundedRectangle.zh-Hans.md) as a background on a [Label](../Label.zh-Hans.md):

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background(in: RoundedRectangle(cornerRadius: 8))
}
```

Without the background modifier, the fill color shows through the label. With the modifier, the label’s text and icon appear backed by a shape filled with a color that’s appropriate for light or dark appearance:



To create a background with other [View](../View.zh-Hans.md) types — or with a stack of views — use [background(alignment:content:)](background_alignment_content.zh-Hans.md) instead. To add a [ShapeStyle](../ShapeStyle.zh-Hans.md) as a background, use [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

