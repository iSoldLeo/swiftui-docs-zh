--- 来源：https://developer.apple.com/documentation/SwiftUI/View/background(ignoresSafeAreaEdges:)

抓取时间：2025-11-30T21:23:20Z

---

# background(ignoresSafeAreaEdges:)

**实例方法**

将视图的背景设置为默认背景样式。

## 声明

```swift
nonisolated func background(ignoresSafeAreaEdges edges: Edge.Set = .all) -> some View

```

## 参数

- **edges**：添加背景时要忽略安全区域内边距的边集。默认值为 [all](../Edge/Set/all.zh-Hans.md)。如果指定空集，则所有边都将遵循安全区域内边距。

## 返回值

一个视图，其后绘制了 [background](../ShapeStyle/background.zh-Hans.md) 形状样式。

## 讨论

此修饰符的行为与 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) 类似，但它始终使用 [background](../ShapeStyle/background.zh-Hans.md) 形状样式。例如，您可以为 [Label](../Label.zh-Hans.md) 添加背景：

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background()
}
```

如果没有背景修饰符，标签后面的青色会透过标签显示出来。使用此修饰符后，标签的文本和图标会显示在填充有适合浅色或深色显示效果的颜色的区域背景中：

如果要指定 [View](../View.zh-Hans.md) 或视图堆栈作为背景，请改用 [background(alignment:content:)](background_alignment_content.zh-Hans.md)。要指定 [Shape](../Shape.zh-Hans.md) 或 [InsettableShape](../InsettableShape.zh-Hans.md)，请使用 [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md)。要配置演示文稿（例如工作表）的背景，请使用 [presentationBackground(_:)](presentationBackground.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：一个覆盖其子视图的视图，并沿两个轴对齐它们。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图之后。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充了样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图的前面。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置包含容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置包含容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/background(ignoresSafeAreaEdges:)
crawled: 2025-11-30T21:23:20Z
---

# background(ignoresSafeAreaEdges:)

**Instance Method**

Sets the view’s background to the default background style.

## Declaration

```swift
nonisolated func background(ignoresSafeAreaEdges edges: Edge.Set = .all) -> some View

```

## Parameters

- **edges**: The set of edges for which to ignore safe area insets when adding the background. The default value is [all](../Edge/Set/all.zh-Hans.md). Specify an empty set to respect safe area insets on all edges.

## Return Value

A view with the [background](../ShapeStyle/background.zh-Hans.md) shape style drawn behind it.

## Discussion

This modifier behaves like [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md), except that it always uses the [background](../ShapeStyle/background.zh-Hans.md) shape style. For example, you can add a background to a [Label](../Label.zh-Hans.md):

```swift
ZStack {
    Color.teal
    Label("Flag", systemImage: "flag.fill")
        .padding()
        .background()
}
```

Without the background modifier, the teal color behind the label shows through the label. With the modifier, the label’s text and icon appear backed by a region filled with a color that’s appropriate for light or dark appearance:



If you want to specify a [View](../View.zh-Hans.md) or a stack of views as the background, use [background(alignment:content:)](background_alignment_content.zh-Hans.md) instead. To specify a [Shape](../Shape.zh-Hans.md) or [InsettableShape](../InsettableShape.zh-Hans.md), use [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md). To configure the background of a presentation, like a sheet, use [presentationBackground(_:)](presentationBackground.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

