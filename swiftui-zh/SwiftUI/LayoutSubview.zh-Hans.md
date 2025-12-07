---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubview
抓取时间： 2025-12-02T16:16:01Z
---

# 布局子视图

**Structure**

表示布局的一个子视图的代理。

### 声明

```swift
struct LayoutSubview
```

## 概览

该类型可作为视图的代理，您的自定义布局容器可将视图放置在用户界面中。[Layout](Layout.zh-Hans.md)协议方法接收一个[LayoutSubviews](LayoutSubviews.zh-Hans.md)集合，该集合包含由容器排列的每个子视图的一个代理。

使用代理可以获取相关子视图的信息，如尺寸、布局优先级或自定义布局值。通过调用代理的[place(at:anchor:proposal:)](LayoutSubview/place_at_anchor_proposal.zh-Hans.md) 方法，还可以使用代理告诉相应的子视图在哪里显示。在实现布局的[placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) 方法时，对每个子视图都要这样做一次。

通过将属性的键作为子视图的索引，可以读取与子视图相关联的自定义布局值。有关定义、设置和读取自定义值的更多信息，请参阅 [LayoutValueKey](LayoutValueKey.zh-Hans.md)。

## 放置子视图

- **place(at:anchor:proposal:)**：为子视图指定位置和大小。

## 获取子视图特征

- **dimensions(in:)**：询问子视图的尺寸和对齐方式。
- **sizeThatFits(_:)**：询问子视图的尺寸。
- **spacing**：子视图的首选间距值。
- **priority**：子视图的布局优先级。

## 获取自定义值

- **subscript(_:)**：获取与指定键相关联的子视图值。

### 实例属性

- **containerValues**：与给定子视图相关联的容器值。

## 创建自定义布局容器

- 使用 SwiftUI 构建自定义布局**：使用 SwiftUI 提供的布局工具在应用程序界面中排列视图。
- **Layout**：定义视图集合几何图形的类型。
- **LayoutSubviews**：表示布局视图子视图的代理值集合。

## 符合

- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview
crawled: 2025-12-02T16:16:01Z
---

# LayoutSubview

**Structure**

A proxy that represents one subview of a layout.

## Declaration

```swift
struct LayoutSubview
```

## Overview

This type acts as a proxy for a view that your custom layout container places in the user interface. [Layout](Layout.zh-Hans.md) protocol methods receive a [LayoutSubviews](LayoutSubviews.zh-Hans.md) collection that contains exactly one proxy for each of the subviews arranged by your container.

Use a proxy to get information about the associated subview, like its dimensions, layout priority, or custom layout values. You also use the proxy to tell its corresponding subview where to appear by calling the proxy’s [place(at:anchor:proposal:)](LayoutSubview/place_at_anchor_proposal.zh-Hans.md) method. Do this once for each subview from your implementation of the layout’s [placeSubviews(in:proposal:subviews:cache:)](Layout/placeSubviews_in_proposal_subviews_cache.zh-Hans.md) method.

You can read custom layout values associated with a subview by using the property’s key as an index on the subview. For more information about defining, setting, and reading custom values, see [LayoutValueKey](LayoutValueKey.zh-Hans.md).

## Placing the subview

- **place(at:anchor:proposal:)**: Assigns a position and proposed size to the subview.

## Getting subview characteristics

- **dimensions(in:)**: Asks the subview for its dimensions and alignment guides.
- **sizeThatFits(_:)**: Asks the subview for its size.
- **spacing**: The subviews’s preferred spacing values.
- **priority**: The layout priority of the subview.

## Getting custom values

- **subscript(_:)**: Gets the value for the subview that’s associated with the specified key.

## Instance Properties

- **containerValues**: The container values associated with the given subview.

## Creating a custom layout container

- **Composing custom layouts with SwiftUI**: Arrange views in your app’s interface using layout tools that SwiftUI provides.
- **Layout**: A type that defines the geometry of a collection of views.
- **LayoutSubviews**: A collection of proxy values that represent the subviews of a layout view.

## Conforms To

- Equatable

