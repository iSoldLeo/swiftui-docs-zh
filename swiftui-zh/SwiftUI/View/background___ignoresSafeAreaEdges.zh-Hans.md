--- 来源：https://developer.apple.com/documentation/SwiftUI/View/background(_:ignoresSafeAreaEdges:)

抓取时间：2025-12-02T17:38:14Z

---

# background(_:ignoresSafeAreaEdges:)

**实例方法**

将视图的背景设置为指定样式。

## 声明

```swift
nonisolated func background<S>(_ style: S, ignoresSafeAreaEdges edges: Edge.Set = .all) -> some View where S : ShapeStyle

```

## 参数

- **style**：符合 [ShapeStyle](../ShapeStyle.zh-Hans.md) 类型的实例，SwiftUI 会将其绘制在修改后的视图后面。

- **edges**：添加背景时要忽略安全区域内边距的边缘集合。默认值为 [all](../Edge/Set/all.zh-Hans.md)。指定一个空集以遵循所有边缘的安全区域内边距。

## 返回值

一个在其后绘制了指定样式的视图。

## 说明

使用此修饰符可以将符合 [ShapeStyle](../ShapeStyle.zh-Hans.md) 协议的类型（例如 [Color](../Color.zh-Hans.md)、[Material](../Material.zh-Hans.md) 或 [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md)）放置在视图的后面。例如，您可以将 [regularMaterial](../ShapeStyle/regularMaterial.zh-Hans.md) 添加到 [Label](../Label.zh-Hans.md) 后面：

```swift
struct FlagLabel: View {
    var body: some View {
        Label("Flag", systemImage: "flag.fill")
            .padding()
            .background(.regularMaterial)
    }
}
```

SwiftUI 将样式锚定到视图的边界。在上面的示例中，背景填充了标签框架的整个区域，包括内边距：

SwiftUI 将背景样式的范围限制在被修改视图相对于容器的形状内。如果您使用 [containerShape(_:)](containerShape.zh-Hans.md) 修改器约束 `FlagLabel` 视图，即可看到此效果：

```swift
FlagLabel()
    .containerShape(RoundedRectangle(cornerRadius: 16))
```

背景将采用指定的容器形状：

默认情况下，背景会忽略所有边上的安全区域内边距，但您可以指定要忽略的边集，或者指定一个空边集以遵循所有边上的安全区域内边距：

```swift
Rectangle()
    .background(
        .regularMaterial,
        ignoresSafeAreaEdges: []) // Ignore no safe area insets.
```

如果您想指定 [View](../View.zh-Hans.md) 或视图堆栈作为背景，请改用 [background(alignment:content:)](background_alignment_content.zh-Hans.md)。要指定 [Shape](../Shape.zh-Hans.md) 或 [InsettableShape](../InsettableShape.zh-Hans.md)，请使用 [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md)。要配置演示文稿（例如工作表）的背景，请使用 [presentationBackground(_:)](presentationBackground.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：一个视图，其子视图会覆盖在此视图之上，并在两个轴上对齐。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图之后。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

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
source: https://developer.apple.com/documentation/SwiftUI/View/background(_:ignoresSafeAreaEdges:)
crawled: 2025-12-02T17:38:14Z
---

# background(_:ignoresSafeAreaEdges:)

**Instance Method**

Sets the view’s background to a style.

## Declaration

```swift
nonisolated func background<S>(_ style: S, ignoresSafeAreaEdges edges: Edge.Set = .all) -> some View where S : ShapeStyle

```

## Parameters

- **style**: An instance of a type that conforms to [ShapeStyle](../ShapeStyle.zh-Hans.md) that SwiftUI draws behind the modified view.
- **edges**: The set of edges for which to ignore safe area insets when adding the background. The default value is [all](../Edge/Set/all.zh-Hans.md). Specify an empty set to respect safe area insets on all edges.

## Return Value

A view with the specified style drawn behind it.

## Discussion

Use this modifier to place a type that conforms to the [ShapeStyle](../ShapeStyle.zh-Hans.md) protocol — like a [Color](../Color.zh-Hans.md), [Material](../Material.zh-Hans.md), or [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md) — behind a view. For example, you can add the [regularMaterial](../ShapeStyle/regularMaterial.zh-Hans.md) behind a [Label](../Label.zh-Hans.md):

```swift
struct FlagLabel: View {
    var body: some View {
        Label("Flag", systemImage: "flag.fill")
            .padding()
            .background(.regularMaterial)
    }
}
```

SwiftUI anchors the style to the view’s bounds. For the example above, the background fills the entirety of the label’s frame, which includes the padding:



SwiftUI limits the background style’s extent to the modified view’s container-relative shape. You can see this effect if you constrain the `FlagLabel` view with a [containerShape(_:)](containerShape.zh-Hans.md) modifier:

```swift
FlagLabel()
    .containerShape(RoundedRectangle(cornerRadius: 16))
```

The background takes on the specified container shape:



By default, the background ignores safe area insets on all edges, but you can provide a specific set of edges to ignore, or an empty set to respect safe area insets on all edges:

```swift
Rectangle()
    .background(
        .regularMaterial,
        ignoresSafeAreaEdges: []) // Ignore no safe area insets.
```

If you want to specify a [View](../View.zh-Hans.md) or a stack of views as the background, use [background(alignment:content:)](background_alignment_content.zh-Hans.md) instead. To specify a [Shape](../Shape.zh-Hans.md) or [InsettableShape](../InsettableShape.zh-Hans.md), use [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md) . To configure the background of a presentation, like a sheet, use [presentationBackground(_:)](presentationBackground.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

