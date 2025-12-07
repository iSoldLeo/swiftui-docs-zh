---

来源：https://developer.apple.com/documentation/SwiftUI/Layout-adjustments
抓取时间：2025-12-02T17:38:23Z

---

# 布局调整

**API 集合**

对对齐方式、间距、内边距和其他布局参数进行微调。

## 概述

堆栈和网格等布局容器为在应用程序的用户界面中排列视图提供了一个很好的起点。当需要进行微调时，请使用布局视图修饰符。您可以调整或约束视图的大小、位置和对齐方式。您还可以为视图添加内边距，并指示视图如何与系统定义的安全区域交互。

要开始使用基本布局，请参阅 [Layout-fundamentals](Layout-fundamentals.zh-Hans.md)。有关设计指南，请参阅人机界面指南中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/layout]。

## 微调布局

- **布局简单视图**：通过调整视图大小来创建视图布局。

- **检查视图布局**：使用 Xcode 预览或添加临时边框来确定视图的位置和范围。

## 为视图添加内边距

- **padding(_:)**：为该视图的每个边缘添加不同的内边距。

- **padding(_:_:)**：为该视图的特定边缘添加相等的内边距。

- **padding3D(_:)**：使用您指定的边缘内边距为该视图添加内边距。

- **padding3D(_:_:)**：使用您指定的边缘内边距为该视图添加内边距。

- **scenePadding(_:)**：使用适合当前场景的内边距为该视图的指定边缘添加内边距。

- **scenePadding(_:edges:)**：为该视图的指定边缘添加指定类型的内边距，内边距的数值根据当前场景而定。

- **ScenePadding**：用于将视图与其包含场景分隔开的内边距。

## 影响视图的大小

- **frame(width:height:alignment:)**：将此视图定位在具有指定大小的不可见框架内。

- **frame(depth:alignment:)**：将此视图定位在具有指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图定位在具有指定大小约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图定位在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **fixedSize()**：将此视图固定在理想大小。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想大小。

- **layoutPriority(_:)**：设置父布局分配给此子视图的空间优先级。

## 调整视图的位置

- **对视图位置进行微调**：通过应用偏移或位置修饰符来移动视图的位置。

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标。

- **offset(_:)**：按偏移参数中指定的水平和垂直量偏移此视图。

- **offset(x:y:)**：按指定的水平和垂直距离偏移此视图。

- **offset(z:)**：将视图沿 Z 轴向前移动指定的距离（以点为单位）。

## 对齐视图

- **在堆栈内对齐视图**：使用对齐参考线在堆栈内定位视图。

- **跨堆栈对齐视图**：创建自定义对齐方式并使用它来对齐多个堆栈中的视图。

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

- **Alignment**：在两个轴上进行对齐。

- **HorizontalAlignment**：沿水平轴的对齐位置。

- **VerticalAlignment**：沿垂直轴的对齐位置。

- **DepthAlignment**：沿深度轴的对齐位置。

- **AlignmentID**：用于创建自定义对齐参考线的类型。

- **ViewDimensions**：视图在其自身坐标空间中的大小和对齐参考线。

- **ViewDimensions3D**：视图在其自身坐标空间中 3D 的大小和对齐参考线。

- **SpatialContainer**：用于在 3D 空间中对齐重叠内容的布局容器。

## 设置边距

- **contentMargins(_:for:)**：配置指定位置的内容边距。

- **contentMargins(_:_:for:)**：配置指定位置的内容边距。

- **ContentMarginPlacement**：边距的位置。

## 保持在安全区域内

- **ignoresSafeArea(_:edges:)**：扩展视图的安全区域。

- **safeAreaInset(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容。

- **safeAreaPadding(_:)**：将指定的内边距添加到此视图的安全区域。

- **safeAreaPadding(_:_:)**：将指定的内边距添加到此视图的安全区域。

- **SafeAreaRegions**：一组符号安全区域。

## 设置布局方向

- **layoutDirectionBehavior(_:)**：设置此视图在不同布局方向上的行为。

- **LayoutDirectionBehavior**：描述布局方向改变时应发生的情况。

- **layoutDirection**：与当前环境关联的布局方向。

- **LayoutDirection**：SwiftUI 可以布局内容的方向。

- **LayoutRotationUnaryLayout**

## 对界面特征做出反应

- **isLuminanceReduced**：一个布尔值，指示当前显示器或环境是否需要降低亮度。

- **displayScale**：此环境的显示缩放比例。

- **pixelLength**：屏幕上像素的大小。

- **horizontalSizeClass**：此环境的水平尺寸类。

- **verticalSizeClass**：此环境的垂直尺寸类。

- **UserInterfaceSizeClass**：一组值，指示视图的可用视觉尺寸。

## 访问边、区域和布局

- **Edge**：枚举值，指示矩形的一条边。

- **Edge3D**：三维体的一个边或面。

- **HorizontalEdge**：水平轴上的边。

- **VerticalEdge**：垂直轴上的边。

- **EdgeInsets**：矩形边的内嵌距离。

- **EdgeInsets3D**：三维体的各个面的内嵌距离。

## 视图布局

- **布局基础**：在内置布局容器（例如堆栈和网格）中排列视图。

- **自定义布局**：以自定义方式排列视图，并在布局类型之间创建动画过渡效果。

- **Lists**：显示结构化的可滚动信息列。

- **Tables**：以行和列的形式显示可选择、可排序的数据。

- **视图分组**：将视图呈现在不同类型的、用途明确的容器中，例如表单或控件组。

- **滚动视图**：允许用户滚动查看当前显示区域之外的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Layout-adjustments
crawled: 2025-12-02T17:38:23Z
---

# Layout adjustments

**API Collection**

Make fine adjustments to alignment, spacing, padding, and other layout parameters.

## Overview

Layout containers like stacks and grids provide a great starting point for arranging views in your app’s user interface. When you need to make fine adjustments, use layout view modifiers. You can adjust or constrain the size, position, and alignment of a view. You can also add padding around a view, and indicate how the view interacts with system-defined safe areas.



To get started with a basic layout, see [Layout-fundamentals](Layout-fundamentals.zh-Hans.md). For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/layout] in the Human Interface Guidelines.

## Finetuning a layout

- **Laying out a simple view**: Create a view layout by adjusting the size of views.
- **Inspecting view layout**: Determine the position and extent of a view using Xcode previews or by adding temporary borders.

## Adding padding around a view

- **padding(_:)**: Adds a different padding amount to each edge of this view.
- **padding(_:_:)**: Adds an equal padding amount to specific edges of this view.
- **padding3D(_:)**: Pads this view using the edge insets you specify.
- **padding3D(_:_:)**: Pads this view using the edge insets you specify.
- **scenePadding(_:)**: Adds padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **scenePadding(_:edges:)**: Adds a specified kind of padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **ScenePadding**: The padding used to space a view from its containing scene.

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

## Adjusting a view’s position

- **Making fine adjustments to a view’s position**: Shift the position of a view by applying the offset or position modifier.
- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.

## Aligning views

- **Aligning views within a stack**: Position views inside a stack using alignment guides.
- **Aligning views across stacks**: Create a custom alignment and use it to align views across multiple stacks.
- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.
- **Alignment**: An alignment in both axes.
- **HorizontalAlignment**: An alignment position along the horizontal axis.
- **VerticalAlignment**: An alignment position along the vertical axis.
- **DepthAlignment**: An alignment position along the depth axis.
- **AlignmentID**: A type that you use to create custom alignment guides.
- **ViewDimensions**: A view’s size and alignment guides in its own coordinate space.
- **ViewDimensions3D**: A view’s 3D size and alignment guides in its own coordinate space.
- **SpatialContainer**: A layout container that aligns overlapping content in 3D space.

## Setting margins

- **contentMargins(_:for:)**: Configures the content margin for a provided placement.
- **contentMargins(_:_:for:)**: Configures the content margin for a provided placement.
- **ContentMarginPlacement**: The placement of margins.

## Staying in the safe areas

- **ignoresSafeArea(_:edges:)**: Expands the safe area of a view.
- **safeAreaInset(edge:alignment:spacing:content:)**: Shows the specified content beside the modified view.
- **safeAreaPadding(_:)**: Adds the provided insets into the safe area of this view.
- **safeAreaPadding(_:_:)**: Adds the provided insets into the safe area of this view.
- **SafeAreaRegions**: A set of symbolic safe area regions.

## Setting a layout direction

- **layoutDirectionBehavior(_:)**: Sets the behavior of this view for different layout directions.
- **LayoutDirectionBehavior**: A description of what should happen when the layout direction changes.
- **layoutDirection**: The layout direction associated with the current environment.
- **LayoutDirection**: A direction in which SwiftUI can lay out content.
- **LayoutRotationUnaryLayout**

## Reacting to interface characteristics

- **isLuminanceReduced**: A Boolean value that indicates whether the display or environment currently requires reduced luminance.
- **displayScale**: The display scale of this environment.
- **pixelLength**: The size of a pixel on the screen.
- **horizontalSizeClass**: The horizontal size class of this environment.
- **verticalSizeClass**: The vertical size class of this environment.
- **UserInterfaceSizeClass**: A set of values that indicate the visual size available to the view.

## Accessing edges, regions, and layouts

- **Edge**: An enumeration to indicate one edge of a rectangle.
- **Edge3D**: An edge or face of a 3D volume.
- **HorizontalEdge**: An edge on the horizontal axis.
- **VerticalEdge**: An edge on the vertical axis.
- **EdgeInsets**: The inset distances for the sides of a rectangle.
- **EdgeInsets3D**: The inset distances for the faces of a 3D volume.

## View layout

- **Layout fundamentals**: Arrange views inside built-in layout containers like stacks and grids.
- **Custom layout**: Place views in custom arrangements and create animated transitions between layout types.
- **Lists**: Display a structured, scrollable column of information.
- **Tables**: Display selectable, sortable data arranged in rows and columns.
- **View groupings**: Present views in different kinds of purpose-driven containers, like forms or control groups.
- **Scroll views**: Enable people to scroll to content that doesn’t fit in the current display.

