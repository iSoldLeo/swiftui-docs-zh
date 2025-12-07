--- 来源：https://developer.apple.com/documentation/SwiftUI/View/background(alignment:content:)

抓取时间：2025-12-02T17:38:14Z

---

# background(alignment:content:)

**实例方法**

将您指定的视图叠加到此视图的后面。

## 声明

```swift
nonisolated func background<V>(alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **alignment**：修饰符用于定位隐式 [ZStack](../ZStack.zh-Hans.md) 的对齐方式，该 [ZStack](../ZStack.zh-Hans.md) 用于对背景视图进行分组。默认值为 [center](../Alignment/center.zh-Hans.md)。

- **content**：用于声明要绘制在此视图后面的视图的 [ViewBuilder](../ViewBuilder.zh-Hans.md)，这些视图按从下到上的级联顺序堆叠。您列出的最后一个视图会出现在堆栈的最前面。

## 返回值

一个使用指定内容作为背景的视图。

## 说明

使用此修饰符可以将一个或多个视图置于另一个视图的后面。例如，您可以将一组星星放置在 [Text](../Text.zh-Hans.md) 视图后面：

```swift
Text("ABCDEF")
    .background(alignment: .leading) { Star(color: .red) }
    .background(alignment: .center) { Star(color: .green) }
    .background(alignment: .trailing) { Star(color: .blue) }
```

以上示例假设您已定义了一个带有参数化颜色的 `Star` 视图：

```swift
struct Star: View {
    var color: Color

    var body: some View {
        Image(systemName: "star.fill")
            .foregroundStyle(color)
    }
}
```

通过为每个修饰符设置不同的 `alignment` 值，您可以使星星出现在文本后面的不同位置：

如果您在 `content` 闭包中指定了多个视图，则该修饰符会将闭包中的所有视图收集到一个隐式的 [ZStack](../ZStack.zh-Hans.md) 中，并按从后到前的顺序排列。例如，您可以将一个竖条置于一个圆的后面，然后将这两个元素都置于一个水平条的后面：

```swift
Color.blue
    .frame(width: 200, height: 10) // Creates a horizontal bar.
    .background {
        Color.green
            .frame(width: 10, height: 100) // Creates a vertical bar.
        Circle()
            .frame(width: 50, height: 50)
    }
```

背景修饰符和由背景内容（圆和竖条）构成的隐式堆栈 [ZStack](../ZStack.zh-Hans.md) 都使用默认的 [center](../Alignment/center.zh-Hans.md) 对齐方式。竖条会居中显示在圆的后面，而圆和竖条则作为一个复合视图居中显示在水平条的后面：

如果您为背景指定了对齐方式，则该对齐方式将应用于隐式堆栈，而不是闭包中的各个视图。添加 [leading](../Alignment/leading.zh-Hans.md) 对齐方式即可看到效果：

```swift
Color.blue
    .frame(width: 200, height: 10)
    .background(alignment: .leading) {
        Color.green
            .frame(width: 10, height: 100)
        Circle()
            .frame(width: 50, height: 50)
    }
```

竖线和圆圈作为一个整体移动，使堆栈与水平线的起始边缘对齐，同时竖线保持在圆圈的中心：

要控制 `content` 闭包内各个项目的位置，可以为每个项目使用不同的背景修饰符（如前面文本下方星形的示例所示），或者在内容闭包内添加一个显式的 [ZStack](../ZStack.zh-Hans.md) 并设置其自身的对齐方式：

```swift
Color.blue
    .frame(width: 200, height: 10)
    .background(alignment: .leading) {
        ZStack(alignment: .leading) {
            Color.green
                .frame(width: 10, height: 100)
            Circle()
                .frame(width: 50, height: 50)
        }
    }
```

堆栈对齐确保圆圈的起始边缘与竖线对齐，而背景修饰符则使复合视图与水平线对齐：

您可以通过将修改后的视图和背景内容都放入 [ZStack](../ZStack.zh-Hans.md) 中来实现无需背景修饰符的图层效果。这样可以简化视图层级结构，但会改变 SwiftUI 应用于视图的布局优先级。如果您希望修改后的视图主导布局，请使用背景修饰符。

如果您想将 [ShapeStyle](../ShapeStyle.zh-Hans.md) 指定为背景，例如 [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md) 或 [Material](../Material.zh-Hans.md)，请改用 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md)。要指定 [Shape](../Shape.zh-Hans.md) 或 [InsettableShape](../InsettableShape.zh-Hans.md)，请使用 [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md)。要配置演示文稿（例如工作表）的背景，请使用 [presentationBackground(alignment:content:)](presentationBackground_alignment_content.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后面创建背景，并将其扩展到安全区域内边距之外。

- **ZStack**：一个覆盖其子视图的视图，并沿两个轴对齐。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图置于此视图的前面。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置外层容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/background(alignment:content:)
crawled: 2025-12-02T17:38:14Z
---

# background(alignment:content:)

**Instance Method**

Layers the views that you specify behind this view.

## Declaration

```swift
nonisolated func background<V>(alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **alignment**: The alignment that the modifier uses to position the implicit [ZStack](../ZStack.zh-Hans.md) that groups the background views. The default is [center](../Alignment/center.zh-Hans.md).
- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that you use to declare the views to draw behind this view, stacked in a cascading order from bottom to top. The last view that you list appears at the front of the stack.

## Return Value

A view that uses the specified content as a background.

## Discussion

Use this modifier to place one or more views behind another view. For example, you can place a collection of stars behind a [Text](../Text.zh-Hans.md) view:

```swift
Text("ABCDEF")
    .background(alignment: .leading) { Star(color: .red) }
    .background(alignment: .center) { Star(color: .green) }
    .background(alignment: .trailing) { Star(color: .blue) }
```

The example above assumes that you’ve defined a `Star` view with a parameterized color:

```swift
struct Star: View {
    var color: Color

    var body: some View {
        Image(systemName: "star.fill")
            .foregroundStyle(color)
    }
}
```

By setting different `alignment` values for each modifier, you make the stars appear in different places behind the text:



If you specify more than one view in the `content` closure, the modifier collects all of the views in the closure into an implicit [ZStack](../ZStack.zh-Hans.md), taking them in order from back to front. For example, you can layer a vertical bar behind a circle, with both of those behind a horizontal bar:

```swift
Color.blue
    .frame(width: 200, height: 10) // Creates a horizontal bar.
    .background {
        Color.green
            .frame(width: 10, height: 100) // Creates a vertical bar.
        Circle()
            .frame(width: 50, height: 50)
    }
```

Both the background modifier and the implicit [ZStack](../ZStack.zh-Hans.md) composed from the background content — the circle and the vertical bar — use a default [center](../Alignment/center.zh-Hans.md) alignment. The vertical bar appears centered behind the circle, and both appear as a composite view centered behind the horizontal bar:



If you specify an alignment for the background, it applies to the implicit stack rather than to the individual views in the closure. You can see this if you add the [leading](../Alignment/leading.zh-Hans.md) alignment:

```swift
Color.blue
    .frame(width: 200, height: 10)
    .background(alignment: .leading) {
        Color.green
            .frame(width: 10, height: 100)
        Circle()
            .frame(width: 50, height: 50)
    }
```

The vertical bar and the circle move as a unit to align the stack with the leading edge of the horizontal bar, while the vertical bar remains centered on the circle:



To control the placement of individual items inside the `content` closure, either use a different background modifier for each item, as the earlier example of stars under text demonstrates, or add an explicit [ZStack](../ZStack.zh-Hans.md) inside the content closure with its own alignment:

```swift
Color.blue
    .frame(width: 200, height: 10)
    .background(alignment: .leading) {
        ZStack(alignment: .leading) {
            Color.green
                .frame(width: 10, height: 100)
            Circle()
                .frame(width: 50, height: 50)
        }
    }
```

The stack alignment ensures that the circle’s leading edge aligns with the vertical bar’s, while the background modifier aligns the composite view with the horizontal bar:



You can achieve layering without a background modifier by putting both the modified view and the background content into a [ZStack](../ZStack.zh-Hans.md). This produces a simpler view hierarchy, but it changes the layout priority that SwiftUI applies to the views. Use the background modifier when you want the modified view to dominate the layout.

If you want to specify a [ShapeStyle](../ShapeStyle.zh-Hans.md) like a [HierarchicalShapeStyle](../HierarchicalShapeStyle.zh-Hans.md) or a [Material](../Material.zh-Hans.md) as the background, use [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) instead. To specify a [Shape](../Shape.zh-Hans.md) or [InsettableShape](../InsettableShape.zh-Hans.md), use [background(_:in:fillStyle:)](background___in_fillStyle.zh-Hans.md). To configure the background of a presentation, like a sheet, use [presentationBackground(alignment:content:)](presentationBackground_alignment_content.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
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

