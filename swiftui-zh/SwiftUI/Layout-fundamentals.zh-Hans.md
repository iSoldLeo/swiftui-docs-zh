---

来源：https://developer.apple.com/documentation/SwiftUI/Layout-fundamentals

抓取时间：2025-12-02T17:39:19Z

---

# 布局基础

**API 集合**

在内置布局容器（例如堆栈和网格）中排列视图。

## 概述

使用布局容器来排列用户界面元素。堆栈和网格会根据内容或界面尺寸的变化更新和调整其包含的子视图的位置。您可以将布局容器嵌套在其他布局容器中，实现任意深度的布局效果。

要微调使用布局容器视图构建的布局的位置、对齐方式和其他元素，请参阅 [Layout-adjustments](Layout-adjustments.zh-Hans.md)。要定义自定义布局容器，请参阅 [Custom-layout](Custom-layout.zh-Hans.md)。有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/layout]。

## 选择布局

- **为内容选择容器视图**：使用堆栈、网格、列表和表单构建灵活的用户界面。

## 静态排列一维视图

- **使用堆栈视图构建布局**：从基本容器视图组合复杂的布局。

- **HStack**：将子视图水平排列的视图。

- **VStack**：将子视图垂直排列的视图。

## 动态排列一维视图

- **使用延迟堆栈视图对数据进行分组**：在延迟堆栈视图中将内容拆分为逻辑部分。

- **创建高性能可滚动堆栈**：使用滚动视图、堆栈视图和延迟堆栈高效地显示大量重复视图。

- **LazyHStack**：一种视图，它将其子视图排列成一行，并沿水平方向扩展，仅在需要时才创建子视图。

- **LazyVStack**：一种视图，它将其子视图排列成一行，并沿垂直方向扩展，仅在需要时才创建子视图。

- **PinnedScrollableViews**：一组可以固定到滚动视图边界的视图类型。

## 静态排列二维视图

- **Grid**：一种容器视图，用于将其他视图排列成二维布局。

- **GridRow**：二维网格容器中的水平行。

- **gridCellColumns(_:)**：指示充当网格单元格的视图跨越指定的列数。

- **gridCellAnchor(_:)**：为用作网格单元格的视图指定自定义对齐锚点。

- **gridCellUnsizedAxes(_:)**：要求网格布局不要在指定的轴上为视图提供额外的尺寸。

- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。

## 动态排列二维视图

- **LazyHGrid**：一种容器视图，它将其子视图排列在一个水平方向扩展的网格中，仅在需要时创建项。

- **LazyVGrid**：一种容器视图，它将其子视图排列在一个垂直方向扩展的网格中，仅在需要时创建项。

- **GridItem**：对惰性网格中的行或列的描述。

## 视图分层

- **为视图添加背景**：在视图后方创建背景，并将其扩展到安全区域之外。

- **ZStack**：一个覆盖其子视图的视图，并沿两个轴对齐它们。

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

- **containerBackground(_:for:)**：使用视图设置包含容器的背景。

- **containerBackground(for:alignment:content:)**：使用视图设置包含容器的背景。

- **ContainerBackgroundPlacement**：容器背景的位置。

## 自动选择合适的布局

- **ViewThatFits**：一种视图，它会根据可用空间自动调整，并提供第一个合适的子视图。

## 分隔符

- **Spacer**：一种灵活的空间，可以沿其所属堆栈布局的主轴扩展；如果未包含在堆栈中，则可以沿两个轴扩展。

- **Divider**：一种可用于分隔其他内容的视觉元素。

## 视图布局

- **布局调整**：对对齐方式、间距、内边距和其他布局参数进行微调。

- **自定义布局**：将视图放置在自定义排列中，并在布局类型之间创建动画过渡效果。

- **Lists**：显示结构化的、可滚动的信息列。

- **Tables**：显示以行和列排列的、可选择和可排序的数据。

- **视图分组**：将视图呈现在不同类型的、用途各异的容器中，例如表单或控件组。

- **滚动视图**：允许用户滚动查看当前显示区域之外的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout-fundamentals
crawled: 2025-12-02T17:39:19Z
---

# Layout fundamentals

**API Collection**

Arrange views inside built-in layout containers like stacks and grids.

## Overview

Use layout containers to arrange the elements of your user interface. Stacks and grids update and adjust the positions of the subviews they contain in response to changes in content or interface dimensions. You can nest layout containers inside other layout containers to any depth to achieve complex layout effects.



To finetune the position, alignment, and other elements of a layout that you build with layout container views, see [Layout-adjustments](Layout-adjustments.zh-Hans.md). To define custom layout containers, see [Custom-layout](Custom-layout.zh-Hans.md). For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/layout] in the Human Interface Guidelines.

## Choosing a layout

- **Picking container views for your content**: Build flexible user interfaces by using stacks, grids, lists, and forms.

## Statically arranging views in one dimension

- **Building layouts with stack views**: Compose complex layouts from primitive container views.
- **HStack**: A view that arranges its subviews in a horizontal line.
- **VStack**: A view that arranges its subviews in a vertical line.

## Dynamically arranging views in one dimension

- **Grouping data with lazy stack views**: Split content into logical sections inside lazy stack views.
- **Creating performant scrollable stacks**: Display large numbers of repeated views efficiently with scroll views, stack views, and lazy stacks.
- **LazyHStack**: A view that arranges its children in a line that grows horizontally, creating items only as needed.
- **LazyVStack**: A view that arranges its children in a line that grows vertically, creating items only as needed.
- **PinnedScrollableViews**: A set of view types that may be pinned to the bounds of a scroll view.

## Statically arranging views in two dimensions

- **Grid**: A container view that arranges other views in a two dimensional layout.
- **GridRow**: A horizontal row in a two dimensional grid container.
- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

## Dynamically arranging views in two dimensions

- **LazyHGrid**: A container view that arranges its child views in a grid that grows horizontally, creating items only as needed.
- **LazyVGrid**: A container view that arranges its child views in a grid that grows vertically, creating items only as needed.
- **GridItem**: A description of a row or a column in a lazy grid.

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
- **ContainerBackgroundPlacement**: The placement of a container background.

## Automatically choosing the layout that fits

- **ViewThatFits**: A view that adapts to the available space by providing the first child view that fits.

## Separators

- **Spacer**: A flexible space that expands along the major axis of its containing stack layout, or on both axes if not contained in a stack.
- **Divider**: A visual element that can be used to separate other content.

## View layout

- **Layout adjustments**: Make fine adjustments to alignment, spacing, padding, and other layout parameters.
- **Custom layout**: Place views in custom arrangements and create animated transitions between layout types.
- **Lists**: Display a structured, scrollable column of information.
- **Tables**: Display selectable, sortable data arranged in rows and columns.
- **View groupings**: Present views in different kinds of purpose-driven containers, like forms or control groups.
- **Scroll views**: Enable people to scroll to content that doesn’t fit in the current display.

