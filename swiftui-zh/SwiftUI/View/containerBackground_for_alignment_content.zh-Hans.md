--- 来源：https://developer.apple.com/documentation/SwiftUI/View/containerBackground(for:alignment:content:)

抓取时间：2025-11-30T21:23:26Z

---

# containerBackground(for:alignment:content:)

**实例方法**

使用视图设置外层容器的背景。

## 声明

```swift
nonisolated func containerBackground<V>(for container: ContainerBackgroundPlacement, alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## 参数

- **container**：将使用背景的容器。

- **alignment**：修饰符用于定位隐式 [ZStack](../ZStack.zh-Hans.md)（用于分组背景视图）的对齐方式。默认值为 [center](../Alignment/center.zh-Hans.md)。

- **content**：用作容器背景的视图。

## 讨论

以下示例使用自定义的 [View](../View.zh-Hans.md) 作为背景：

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("Image") {
                    Text("Image")
                    .containerBackground(for: .navigation) {
                        Image(name: "ImageAsset")
                    }
                }
            }
        }
    }
}
```

`.containerBackground(for:alignment:content:)` 修饰符与 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) 修饰符的区别在于，它会自动填充整个父容器。[ContainerBackgroundPlacement](../ContainerBackgroundPlacement.zh-Hans.md) 描述了可用的容器。

## 视图分层

- **为视图添加背景**：在视图后面创建背景，并将其扩展到安全区域之外。

- **ZStack**：覆盖其子视图的视图，并在两个轴上对齐它们。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的下方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图置于此视图的前方。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式置于此视图的前方。

- **overlay(_:in:fillStyle:)**：将您指定的形状置于此视图的前方。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：设置视图所包含容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/containerBackground(for:alignment:content:)
crawled: 2025-11-30T21:23:26Z
---

# containerBackground(for:alignment:content:)

**Instance Method**

Sets the container background of the enclosing container using a view.

## Declaration

```swift
nonisolated func containerBackground<V>(for container: ContainerBackgroundPlacement, alignment: Alignment = .center, @ViewBuilder content: () -> V) -> some View where V : View

```

## Parameters

- **container**: The container that will use the background.
- **alignment**: The alignment that the modifier uses to position the implicit [ZStack](../ZStack.zh-Hans.md) that groups the background views. The default is [center](../Alignment/center.zh-Hans.md).
- **content**: The view to use as the background of the container.

## Discussion

The following example uses a custom [View](../View.zh-Hans.md) as a background:

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("Image") {
                    Text("Image")
                    .containerBackground(for: .navigation) {
                        Image(name: "ImageAsset")
                    }
                }
            }
        }
    }
}
```

The `.containerBackground(for:alignment:content:)` modifier differs from the [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) modifier by automatically filling an entire parent container. [ContainerBackgroundPlacement](../ContainerBackgroundPlacement.zh-Hans.md) describes the available containers.

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
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.
- **backgroundMaterial**: The material underneath the current view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

