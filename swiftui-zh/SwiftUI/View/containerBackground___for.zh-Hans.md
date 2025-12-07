--- 来源：https://developer.apple.com/documentation/SwiftUI/View/containerBackground(_:for:)

抓取时间：2025-11-30T21:23:25Z

---

# containerBackground(_:for:)

**实例方法**

使用视图设置外层容器的背景。

## 声明

```swift
nonisolated func containerBackground<S>(_ style: S, for container: ContainerBackgroundPlacement) -> some View where S : ShapeStyle

```

## 说明

以下示例使用 [LinearGradient](../LinearGradient.zh-Hans.md) 作为背景：

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("Blue") {
                    Text("Blue")
                    .containerBackground(.blue.gradient, for: .navigation)
                }
                NavigationLink("Red") {
                    Text("Red")
                    .containerBackground(.red.gradient, for: .navigation)
                }
            }
        }
    }
}
```

`.containerBackground(_:for:)` 修饰符与 [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) 修饰符的区别在于，它会自动填充整个父容器。[ContainerBackgroundPlacement](../ContainerBackgroundPlacement.zh-Hans.md) 描述了可用的容器。

- 参数

- style：用作容器背景的形状样式。

- container：将使用背景的容器。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：覆盖其子视图的视图，并在两个轴上对齐它们。

- **zIndex(_:)**：控制重叠视图的显示顺序。

- **background(alignment:content:)**：将您指定的视图置于此视图的后方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充了指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图的前面。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(for:alignment:content:)**：使用视图设置包含容器的容器背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/containerBackground(_:for:)
crawled: 2025-11-30T21:23:25Z
---

# containerBackground(_:for:)

**Instance Method**

Sets the container background of the enclosing container using a view.

## Declaration

```swift
nonisolated func containerBackground<S>(_ style: S, for container: ContainerBackgroundPlacement) -> some View where S : ShapeStyle

```

## Discussion

The following example uses a [LinearGradient](../LinearGradient.zh-Hans.md) as a background:

```swift
struct ContentView: View {
    var body: some View {
        NavigationStack {
            List {
                NavigationLink("Blue") {
                    Text("Blue")
                    .containerBackground(.blue.gradient, for: .navigation)
                }
                NavigationLink("Red") {
                    Text("Red")
                    .containerBackground(.red.gradient, for: .navigation)
                }
            }
        }
    }
}
```

The `.containerBackground(_:for:)` modifier differs from the [background(_:ignoresSafeAreaEdges:)](background___ignoresSafeAreaEdges.zh-Hans.md) modifier by automatically filling an entire parent container. [ContainerBackgroundPlacement](../ContainerBackgroundPlacement.zh-Hans.md) describes the available containers.

- Parameters

- style: The shape style to use as the container background.
- container: The container that will use the background.

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
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

