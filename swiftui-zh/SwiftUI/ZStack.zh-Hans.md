---
来源： https://developer.apple.com/documentation/SwiftUI/ZStack
抓取时间： 2025-12-02T16:24:16Z
---

# ZStack

**Structure**

一种视图，可覆盖其子视图，并在两个轴上对齐。

## 声明

```swift
@frozen struct ZStack<Content> where Content : View
```

## 概览

`ZStack`会为每个连续的子视图分配一个比前一个更高的 Z 轴值，这意味着后面的子视图会出现在前面的子视图的 "顶部"。

下面的示例创建了一个由 100 x 100 点[Rectangle](Rectangle.zh-Hans.md) 视图组成的`ZStack`，视图填充了六种颜色中的一种，每个连续的子视图偏移 10 点，这样它们就不会完全重叠：

```swift
let colors: [Color] =
    [.red, .orange, .yellow, .green, .blue, .purple]

var body: some View {
    ZStack {
        ForEach(0..<colors.count) {
            Rectangle()
                .fill(colors[$0])
                .frame(width: 100, height: 100)
                .offset(x: CGFloat($0) * 10.0,
                        y: CGFloat($0) * 10.0)
        }
    }
}
```



`ZStack`使用[Alignment](Alignment.zh-Hans.md)设置每个子视图的 x 轴和 y 轴坐标，默认对齐方式为[center](Alignment/center.zh-Hans.md)。在下面的示例中，`ZStack` 使用[bottomLeading](Alignment/bottomLeading.zh-Hans.md) 对齐方式布局了两个子视图，下面是一个 100 x 50 点的红色矩形，上面是一个 50 x 100 点的蓝色矩形。由于对齐值的原因，两个矩形都与`ZStack`共享一个左下角（在以左为前导侧的地方）。

```swift
var body: some View {
    ZStack(alignment: .bottomLeading) {
        Rectangle()
            .fill(Color.red)
            .frame(width: 100, height: 50)
        Rectangle()
            .fill(Color.blue)
            .frame(width:50, height: 100)
    }
    .border(Color.green, width: 1)
}
```





## 创建堆栈

- **init(alignment:content:)**：以给定的对齐方式创建一个实例。

## 支持符号

- **ZStackContent3D**：为[ZStack](ZStack.zh-Hans.md)添加间距的类型。

## 初始化器

- **init(alignment:spacing:content:)**：创建一个具有指定间距和对齐方式的实例。

## 分层视图

- 为视图添加背景**：在视图后添加背景，并将其扩展到安全区域嵌套之外。
- **zIndex(_:)**：控制重叠视图的显示顺序。
- **background(alignment:content:)**：将您指定的视图分层显示在此视图后面。
- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为某种样式。
- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。
- **background(_:in:fillStyle:)**：将视图背景设置为默认背景样式：将视图的背景设置为填充样式的可插入形状。
- **background(in:fillStyle:)**：将视图的背景设置为使用默认背景样式填充的可插入形状。
- **overlay(alignment:content:)**：将您指定的视图分层显示在该视图前面。
- **overlay(_:ignoresSafeAreaEdges:)**：在此视图前面分层指定的样式。
- **overlay(_:in:fillStyle:)**：在此视图前分层显示指定的形状。
- **backgroundMaterial**：当前视图下方的材质。
- **containerBackground(_:for:)**：设置使用视图的包围容器的容器背景。
- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的容器背景。
- **ContainerBackgroundPlacement**：容器背景的位置。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/ZStack
crawled: 2025-12-02T16:24:16Z
---

# ZStack

**Structure**

A view that overlays its subviews, aligning them in both axes.

## Declaration

```swift
@frozen struct ZStack<Content> where Content : View
```

## Overview

The `ZStack` assigns each successive subview a higher z-axis value than the one before it, meaning later subviews appear “on top” of earlier ones.

The following example creates a `ZStack` of 100 x 100 point [Rectangle](Rectangle.zh-Hans.md) views filled with one of six colors, offsetting each successive subview by 10 points so they don’t completely overlap:

```swift
let colors: [Color] =
    [.red, .orange, .yellow, .green, .blue, .purple]

var body: some View {
    ZStack {
        ForEach(0..<colors.count) {
            Rectangle()
                .fill(colors[$0])
                .frame(width: 100, height: 100)
                .offset(x: CGFloat($0) * 10.0,
                        y: CGFloat($0) * 10.0)
        }
    }
}
```



The `ZStack` uses an [Alignment](Alignment.zh-Hans.md) to set the x- and y-axis coordinates of each subview, defaulting to a [center](Alignment/center.zh-Hans.md) alignment. In the following example, the `ZStack` uses a [bottomLeading](Alignment/bottomLeading.zh-Hans.md) alignment to lay out two subviews, a red 100 x 50 point rectangle below, and a blue 50 x 100 point rectangle on top. Because of the alignment value, both rectangles share a bottom-left corner with the `ZStack` (in locales where left is the leading side).

```swift
var body: some View {
    ZStack(alignment: .bottomLeading) {
        Rectangle()
            .fill(Color.red)
            .frame(width: 100, height: 50)
        Rectangle()
            .fill(Color.blue)
            .frame(width:50, height: 100)
    }
    .border(Color.green, width: 1)
}
```





## Creating a stack

- **init(alignment:content:)**: Creates an instance with the given alignment.

## Supporting symbols

- **ZStackContent3D**: A type that adds spacing to a [ZStack](ZStack.zh-Hans.md).

## Initializers

- **init(alignment:spacing:content:)**: Creates an instance with the given spacing and alignment.

## Layering views

- **Adding a background to your view**: Compose a background behind your view and extend it beyond the safe area insets.
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
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

## Conforms To

- View

