---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/backgroundmaterial
抓取时间： 2025-12-04T13:10:31Z
---

# 背景材料

**实例属性**

当前视图下方的材质。

## 声明

```swift
var backgroundMaterial: Material? { get set }
```

## 讨论

如果当前背景不是标准材质之一，则此值为`nil`。如果设置了材质，标准内容样式就会启用其生动的渲染模式。

您可以通过调用其中一个包含[ShapeStyle](../ShapeStyle.zh-Hans.md)（如[background(_:ignoresSafeAreaEdges:)](../View/background___ignoresSafeAreaEdges.zh-Hans.md)或[background(_:in:fillStyle:)](../View/background___in_fillStyle.zh-Hans.md)）的背景修改器，并传入[Material](../Material.zh-Hans.md)来设置该值。您也可以手动设置该值，使用 `nil` 禁用鲜艳渲染，或使用 [Material](../Material.zh-Hans.md) 实例启用与指定材质相关的鲜艳样式。

## 分层视图

- 为视图添加背景**：在视图后添加背景，并将其扩展到安全区域嵌套之外。
- **ZStack**：覆盖子视图的视图，在两个轴上对齐。
- **zIndex(_:)**：控制重叠视图的显示顺序。
- **background(alignment:content:)**：将您指定的视图分层显示在此视图后面。
- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为某种样式。
- **background(ignoresSafeAreaEdges:)**：将视图背景设置为样式：将视图的背景设置为默认背景样式。
- **background(_:in:fillStyle:)**：将视图背景设置为默认背景样式：将视图的背景设置为填充样式的可插入形状。
- **background(in:fillStyle:)**：将视图的背景设置为使用默认背景样式填充的可插入形状。
- **overlay(alignment:content:)**：将您指定的视图分层显示在该视图前面。
- **overlay(_:ignoresSafeAreaEdges:)**：在此视图前面分层指定的样式。
- **overlay(_:in:fillStyle:)**：在此视图前面分层指定的形状。
- **containerBackground(_:for:)**：设置使用视图的包围容器的容器背景。
- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的容器背景。
- **ContainerBackgroundPlacement**：容器背景的位置。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/backgroundmaterial
crawled: 2025-12-04T13:10:31Z
---

# backgroundMaterial

**Instance Property**

The material underneath the current view.

## Declaration

```swift
var backgroundMaterial: Material? { get set }
```

## Discussion

This value is `nil` if the current background isn’t one of the standard materials. If you set a material, the standard content styles enable their vibrant rendering modes.

You set this value by calling one of the background modifiers that takes a [ShapeStyle](../ShapeStyle.zh-Hans.md), like [background(_:ignoresSafeAreaEdges:)](../View/background___ignoresSafeAreaEdges.zh-Hans.md) or [background(_:in:fillStyle:)](../View/background___in_fillStyle.zh-Hans.md), and passing in a [Material](../Material.zh-Hans.md). You can also set the value manually, using `nil` to disable vibrant rendering, or a [Material](../Material.zh-Hans.md) instance to enable the vibrancy style associated with the specified material.

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
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **ContainerBackgroundPlacement**: The placement of a container background.

