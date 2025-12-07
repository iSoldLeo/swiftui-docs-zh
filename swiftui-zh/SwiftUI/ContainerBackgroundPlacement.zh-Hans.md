---
来源： https://developer.apple.com/documentation/SwiftUI/ContainerBackgroundPlacement
抓取时间： 2025-12-02T17:38:22Z
---

# ContainerBackgroundPlacement

**Structure**

容器背景的位置。

## 声明

```swift
struct ContainerBackgroundPlacement
```

## 概览

此方法控制使用 [containerBackground(_:for:)](View/containerBackground___for.zh-Hans.md) 或 [containerBackground(for:alignment:content:)](View/containerBackground_for_alignment_content.zh-Hans.md) 修饰符指定的背景的位置。

## 获取位置

- **navigation**：[NavigationStack](NavigationStack.zh-Hans.md)或[NavigationSplitView](NavigationSplitView.zh-Hans.md)内的背景位置。
- **tabView**：[TabView](TabView.zh-Hans.md)内的背景位置。
- **widget**：部件的容器背景位置。

## 获取 StoreKit 放置位置

- **subscriptionStore**：订阅商店视图中的自动位置，基于视图的上下文。
- **subscriptionStoreFullHeight**：跨越订阅商店视图整个高度的背景位置。
- **subscriptionStoreHeader**：订阅商店视图营销内容后面的背景位置。

### 类型属性

- **navigationSplitView**：[NavigationSplitView](NavigationSplitView.zh-Hans.md)内容后面的背景位置。
- **window**：[Window](Window.zh-Hans.md)或[WindowGroup](WindowGroup.zh-Hans.md)内的背景位置。

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
- **overlay(_:in:fillStyle:)**：在此视图前分层显示指定的形状。
- **backgroundMaterial**：当前视图下方的材质。
- **containerBackground(_:for:)**：设置使用视图的包围容器的容器背景。
- **containerBackground(for:alignment:content:)**：使用视图设置外层容器的容器背景。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerBackgroundPlacement
crawled: 2025-12-02T17:38:22Z
---

# ContainerBackgroundPlacement

**Structure**

The placement of a container background.

## Declaration

```swift
struct ContainerBackgroundPlacement
```

## Overview

This method controls where to place a background that you specify with the [containerBackground(_:for:)](View/containerBackground___for.zh-Hans.md) or [containerBackground(for:alignment:content:)](View/containerBackground_for_alignment_content.zh-Hans.md) modifier.

## Getting placements

- **navigation**: A background placement inside a [NavigationStack](NavigationStack.zh-Hans.md) or [NavigationSplitView](NavigationSplitView.zh-Hans.md).
- **tabView**: A background placement inside a [TabView](TabView.zh-Hans.md).
- **widget**: The container background placement for a widget.

## Getting StoreKit placements

- **subscriptionStore**: An automatic placement within a subscription store view, based on the view’s context.
- **subscriptionStoreFullHeight**: A background placement that spans the full height of a subscription store view.
- **subscriptionStoreHeader**: A background placement behind the marketing content of a subscription store view.

## Type Properties

- **navigationSplitView**: A background placement behind the content of a [NavigationSplitView](NavigationSplitView.zh-Hans.md).
- **window**: A  background placement inside a [Window](Window.zh-Hans.md) or [WindowGroup](WindowGroup.zh-Hans.md)

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
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

