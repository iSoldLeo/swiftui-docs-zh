--- 来源：https://developer.apple.com/documentation/SwiftUI/View/zIndex(_:)

抓取时间：2025-12-02T17:38:13Z

---

# zIndex(_:)

**实例方法**

控制重叠视图的显示顺序。

## 声明

```swift
nonisolated func zIndex(_ value: Double) -> some View

```

## 参数

- **value**：此视图的相对前后顺序；默认值为 `0`。

## 说明

当需要控制视图的前后顺序时，请使用 `zIndex(_:)`。

在本例中，有两个重叠的旋转矩形。索引值较大的矩形位于最前面。

```swift
VStack {
    Rectangle()
        .fill(Color.yellow)
        .frame(width: 100, height: 100, alignment: .center)
        .zIndex(1) // Top layer.

    Rectangle()
        .fill(Color.red)
        .frame(width: 100, height: 100, alignment: .center)
        .rotationEffect(.degrees(45))
        // Here a zIndex of 0 is the default making
        // this the bottom layer.
}
```

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：将子视图叠加到视图上，并在两个轴上对齐。

- **background(alignment:content:)**：将您指定的视图分层到此视图的后方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图的前面。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

- **backgroundMaterial**：当前视图下方的材质。

- **containerBackground(_:for:)**：使用视图设置外层容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/zIndex(_:)
crawled: 2025-12-02T17:38:13Z
---

# zIndex(_:)

**Instance Method**

Controls the display order of overlapping views.

## Declaration

```swift
nonisolated func zIndex(_ value: Double) -> some View

```

## Parameters

- **value**: A relative front-to-back ordering for this view; the default is `0`.

## Discussion

Use `zIndex(_:)` when you want to control the front-to-back ordering of views.

In this example there are two overlapping rotated rectangles. The frontmost is represented by the larger index value.

```swift
VStack {
    Rectangle()
        .fill(Color.yellow)
        .frame(width: 100, height: 100, alignment: .center)
        .zIndex(1) // Top layer.

    Rectangle()
        .fill(Color.red)
        .frame(width: 100, height: 100, alignment: .center)
        .rotationEffect(.degrees(45))
        // Here a zIndex of 0 is the default making
        // this the bottom layer.
}
```



## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
- **ZStack**: A view that overlays its subviews, aligning them in both axes.
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
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

