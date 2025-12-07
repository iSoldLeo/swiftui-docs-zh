--- 来源：https://developer.apple.com/documentation/SwiftUI/View/overlay(alignment:content:)

抓取时间：2025-11-30T21:23:22Z

---

# overlay(alignment:content:)

**实例方法**

将您指定的视图叠加到此视图的前面。

## 声明

```swift
nonisolated func overlay<V>(alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **alignment**：修饰符用于定位隐式 [ZStack](../ZStack.zh-Hans.md) 的对齐方式，该 [ZStack](../ZStack.zh-Hans.md) 用于对前景视图进行分组。默认值为 [center](../Alignment/center.zh-Hans.md)。

- **content**：用于声明要绘制在此视图前面的视图的 [ViewBuilder](../ViewBuilder.zh-Hans.md)，这些视图将按照您列出的顺序堆叠。您列出的最后一个视图会出现在堆栈的最前面。

## 返回值

一个使用指定内容作为前景的视图。

## 说明

使用此修饰符可以将一个或多个视图置于另一个视图的前面。例如，您可以将一组星形放置在 [RoundedRectangle](../RoundedRectangle.zh-Hans.md) 上：

```swift
RoundedRectangle(cornerRadius: 8)
    .frame(width: 200, height: 100)
    .overlay(alignment: .topLeading) { Star(color: .red) }
    .overlay(alignment: .topTrailing) { Star(color: .yellow) }
    .overlay(alignment: .bottomLeading) { Star(color: .green) }
    .overlay(alignment: .bottomTrailing) { Star(color: .blue) }
```

以上示例假设您已定义了一个带有参数化颜色的 `Star` 视图：

```swift
struct Star: View {
    var color = Color.yellow

    var body: some View {
        Image(systemName: "star.fill")
            .foregroundStyle(color)
    }
}
```

通过为每个修饰符设置不同的 `alignment` 值，您可以使星形出现在矩形上的不同位置：

如果您在 `content` 闭包中指定了多个视图，则修饰符会将闭包中的所有视图收集到一个隐式的 [ZStack](../ZStack.zh-Hans.md) 中，并按从后到前的顺序进行排列。例如，您可以在 [blue](../ShapeStyle/blue.zh-Hans.md) 区域上放置一个星形和一个 [Circle](../Circle.zh-Hans.md)：

```swift
Color.blue
    .frame(width: 200, height: 200)
    .overlay {
        Circle()
            .frame(width: 100, height: 100)
        Star()
    }
```

叠加修饰符和由叠加内容（圆形和星形）组成的隐式 [ZStack](../ZStack.zh-Hans.md) 都使用默认的 [center](../Alignment/center.zh-Hans.md) 对齐方式。星形显示在圆形的中心，两者显示为一个复合视图，位于正方形的正前方：

如果您为叠加指定了对齐方式，则该对齐方式将应用于隐式堆栈，而不是闭包中的各个视图。如果您添加 [bottom](../Alignment/bottom.zh-Hans.md) 对齐方式，就能看到这一点：

```swift
Color.blue
    .frame(width: 200, height: 200)
    .overlay(alignment: .bottom) {
        Circle()
            .frame(width: 100, height: 100)
        Star()
    }
```

圆和星形作为一个整体向下移动，使堆栈的底边与正方形的底边对齐，同时星形保持在圆的中心：

要控制 `content` 闭包内各个项目的位置，您可以为每个项目使用不同的叠加修改器（如前面矩形角上的星形示例所示），或者在内容闭包内添加一个显式的 [ZStack](../ZStack.zh-Hans.md) 对齐方式，并为其设置自己的对齐方式：

```swift
Color.blue
    .frame(width: 200, height: 200)
    .overlay(alignment: .bottom) {
        ZStack(alignment: .bottom) {
            Circle()
                .frame(width: 100, height: 100)
            Star()
        }
    }
```

堆栈对齐方式确保星形的底边与圆的底边对齐，而叠加方式则使复合视图与正方形对齐：

您可以通过将修改后的视图和叠加内容都放入一个 中来实现无需叠加修改器的图层效果。 [ZStack](../ZStack.zh-Hans.md)。这可以简化视图层级结构，但会改变 SwiftUI 应用于视图的布局优先级。如果您希望修改后的视图主导布局，请使用 overlay 修饰符。

如果您想将 [ShapeStyle](../ShapeStyle.zh-Hans.md) 指定为类似 [Color](../Color.zh-Hans.md) 或 [Material](../Material.zh-Hans.md) 的 overlay，请改用 [overlay(_:ignoresSafeAreaEdges:)](overlay___ignoresSafeAreaEdges.zh-Hans.md)。要指定 [Shape](../Shape.zh-Hans.md)，请使用 [overlay(_:in:fillStyle:)](overlay___in_fillStyle.zh-Hans.md)。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域内边距之外。

- **ZStack**：覆盖其子视图的视图，使它们在两个轴上对齐。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的下方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式置于此视图的上方。

- **overlay(_:in:fillStyle:)**：将您指定的形状置于此视图的上方。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：设置视图的容器背景。

- **containerBackground(for:alignment:content:)**：设置视图的容器背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/overlay(alignment:content:)
crawled: 2025-11-30T21:23:22Z
---

# overlay(alignment:content:)

**Instance Method**

Layers the views that you specify in front of this view.

## Declaration

```swift
nonisolated func overlay<V>(alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **alignment**: The alignment that the modifier uses to position the implicit [ZStack](../ZStack.zh-Hans.md) that groups the foreground views. The default is [center](../Alignment/center.zh-Hans.md).
- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that you use to declare the views to draw in front of this view, stacked in the order that you list them. The last view that you list appears at the front of the stack.

## Return Value

A view that uses the specified content as a foreground.

## Discussion

Use this modifier to place one or more views in front of another view. For example, you can place a group of stars on a [RoundedRectangle](../RoundedRectangle.zh-Hans.md):

```swift
RoundedRectangle(cornerRadius: 8)
    .frame(width: 200, height: 100)
    .overlay(alignment: .topLeading) { Star(color: .red) }
    .overlay(alignment: .topTrailing) { Star(color: .yellow) }
    .overlay(alignment: .bottomLeading) { Star(color: .green) }
    .overlay(alignment: .bottomTrailing) { Star(color: .blue) }
```

The example above assumes that you’ve defined a `Star` view with a parameterized color:

```swift
struct Star: View {
    var color = Color.yellow

    var body: some View {
        Image(systemName: "star.fill")
            .foregroundStyle(color)
    }
}
```

By setting different `alignment` values for each modifier, you make the stars appear in different places on the rectangle:



If you specify more than one view in the `content` closure, the modifier collects all of the views in the closure into an implicit [ZStack](../ZStack.zh-Hans.md), taking them in order from back to front. For example, you can place a star and a [Circle](../Circle.zh-Hans.md) on a field of [blue](../ShapeStyle/blue.zh-Hans.md):

```swift
Color.blue
    .frame(width: 200, height: 200)
    .overlay {
        Circle()
            .frame(width: 100, height: 100)
        Star()
    }
```

Both the overlay modifier and the implicit [ZStack](../ZStack.zh-Hans.md) composed from the overlay content — the circle and the star — use a default [center](../Alignment/center.zh-Hans.md) alignment. The star appears centered on the circle, and both appear as a composite view centered in front of the square:



If you specify an alignment for the overlay, it applies to the implicit stack rather than to the individual views in the closure. You can see this if you add the [bottom](../Alignment/bottom.zh-Hans.md) alignment:

```swift
Color.blue
    .frame(width: 200, height: 200)
    .overlay(alignment: .bottom) {
        Circle()
            .frame(width: 100, height: 100)
        Star()
    }
```

The circle and the star move down as a unit to align the stack’s bottom edge with the bottom edge of the square, while the star remains centered on the circle:



To control the placement of individual items inside the `content` closure, either use a different overlay modifier for each item, as the earlier example of stars in the corners of a rectangle demonstrates, or add an explicit [ZStack](../ZStack.zh-Hans.md) inside the content closure with its own alignment:

```swift
Color.blue
    .frame(width: 200, height: 200)
    .overlay(alignment: .bottom) {
        ZStack(alignment: .bottom) {
            Circle()
                .frame(width: 100, height: 100)
            Star()
        }
    }
```

The stack alignment ensures that the star’s bottom edge aligns with the circle’s, while the overlay aligns the composite view with the square:



You can achieve layering without an overlay modifier by putting both the modified view and the overlay content into a [ZStack](../ZStack.zh-Hans.md). This can produce a simpler view hierarchy, but changes the layout priority that SwiftUI applies to the views. Use the overlay modifier when you want the modified view to dominate the layout.

If you want to specify a [ShapeStyle](../ShapeStyle.zh-Hans.md) like a [Color](../Color.zh-Hans.md) or a [Material](../Material.zh-Hans.md) as the overlay, use [overlay(_:ignoresSafeAreaEdges:)](overlay___ignoresSafeAreaEdges.zh-Hans.md) instead. To specify a [Shape](../Shape.zh-Hans.md), use [overlay(_:in:fillStyle:)](overlay___in_fillStyle.zh-Hans.md).

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
- **zIndex(_:)**: Controls the display order of overlapping views.
- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

