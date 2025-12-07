--- 来源：https://developer.apple.com/documentation/SwiftUI/View/overlay(_:ignoresSafeAreaEdges:)

抓取时间：2025-11-30T21:23:23Z

---

# overlay(_:ignoresSafeAreaEdges:)

**实例方法**

将指定的样式叠加到此视图的前面。

## 声明

```swift
nonisolated func overlay<S>(_ style: S, ignoresSafeAreaEdges edges: Edge.Set = .all) -> some View where S : ShapeStyle

```

## 参数

- **style**：符合 [ShapeStyle](../ShapeStyle.zh-Hans.md) 类型的实例，SwiftUI 会将其叠加到修改后的视图前面。

- **edges**：添加叠加层时要忽略安全区域内边距的边缘集。默认值为 [all](../Edge/Set/all.zh-Hans.md)。指定一个空集以遵循所有边缘的安全区域内边距。

## 返回值

一个在其前面绘制了指定样式的视图。

## 说明

使用此修饰符可以将符合 [ShapeStyle](../ShapeStyle.zh-Hans.md) 协议的类型（例如 [Color](../Color.zh-Hans.md)、[Material](../Material.zh-Hans.md) 或 [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md)）叠加在视图前面。例如，您可以将 [ultraThinMaterial](../ShapeStyle/ultraThinMaterial.zh-Hans.md) 叠加在 [Circle](../Circle.zh-Hans.md) 之上：

```swift
struct CoveredCircle: View {
    var body: some View {
        Circle()
            .frame(width: 300, height: 200)
            .overlay(.ultraThinMaterial)
    }
}
```

SwiftUI 会将样式锚定到视图的边界。在上面的示例中，叠加层填充了整个圆的框架（恰好比圆的高度宽）：

SwiftUI 还会将样式的范围限制在视图相对于容器的形状内。如果您使用 [containerShape(_:)](containerShape.zh-Hans.md) 修改器约束 `CoveredCircle` 视图，即可看到此效果：

```swift
CoveredCircle()
    .containerShape(RoundedRectangle(cornerRadius: 30))
```

叠加层会采用指定的容器形状：

默认情况下，叠加层会忽略所有边上的安全区域内边距，但您可以指定要忽略的边集，或者指定一个空边集以遵循所有边上的安全区域内边距：

```swift
Rectangle()
    .overlay(
        .secondary,
        ignoresSafeAreaEdges: []) // Ignore no safe area insets.
```

如果您想指定 [View](../View.zh-Hans.md) 或视图堆栈作为叠加层而不是样式，请改用 [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md)。如果您想指定 [Shape](../Shape.zh-Hans.md)，请使用 [overlay(_:in:fillStyle:)](overlay___in_fillStyle.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：一个覆盖其子视图的视图，并沿两个轴对齐。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的后方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充了指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置包含容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置包含容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/overlay(_:ignoresSafeAreaEdges:)
crawled: 2025-11-30T21:23:23Z
---

# overlay(_:ignoresSafeAreaEdges:)

**Instance Method**

Layers the specified style in front of this view.

## Declaration

```swift
nonisolated func overlay<S>(_ style: S, ignoresSafeAreaEdges edges: Edge.Set = .all) -> some View where S : ShapeStyle

```

## Parameters

- **style**: An instance of a type that conforms to [ShapeStyle](../ShapeStyle.zh-Hans.md) that SwiftUI layers in front of the modified view.
- **edges**: The set of edges for which to ignore safe area insets when adding the overlay. The default value is [all](../Edge/Set/all.zh-Hans.md). Specify an empty set to respect safe area insets on all edges.

## Return Value

A view with the specified style drawn in front of it.

## Discussion

Use this modifier to layer a type that conforms to the [ShapeStyle](../ShapeStyle.zh-Hans.md) protocol, like a [Color](../Color.zh-Hans.md), [Material](../Material.zh-Hans.md), or [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md), in front of a view. For example, you can overlay the [ultraThinMaterial](../ShapeStyle/ultraThinMaterial.zh-Hans.md) over a [Circle](../Circle.zh-Hans.md):

```swift
struct CoveredCircle: View {
    var body: some View {
        Circle()
            .frame(width: 300, height: 200)
            .overlay(.ultraThinMaterial)
    }
}
```

SwiftUI anchors the style to the view’s bounds. For the example above, the overlay fills the entirety of the circle’s frame (which happens to be wider than the circle is tall):



SwiftUI also limits the style’s extent to the view’s container-relative shape. You can see this effect if you constrain the `CoveredCircle` view with a [containerShape(_:)](containerShape.zh-Hans.md) modifier:

```swift
CoveredCircle()
    .containerShape(RoundedRectangle(cornerRadius: 30))
```

The overlay takes on the specified container shape:



By default, the overlay ignores safe area insets on all edges, but you can provide a specific set of edges to ignore, or an empty set to respect safe area insets on all edges:

```swift
Rectangle()
    .overlay(
        .secondary,
        ignoresSafeAreaEdges: []) // Ignore no safe area insets.
```

If you want to specify a [View](../View.zh-Hans.md) or a stack of views as the overlay rather than a style, use [overlay(alignment:content:)](overlay_alignment_content.zh-Hans.md) instead. If you want to specify a [Shape](../Shape.zh-Hans.md), use [overlay(_:in:fillStyle:)](overlay___in_fillStyle.zh-Hans.md).

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
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

