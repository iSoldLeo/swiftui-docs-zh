---

来源：https://developer.apple.com/documentation/SwiftUI/View-Layout

抓取时间：2025-12-02T17:22:14Z

---

# 布局修饰符

**API 集合**

通过调整视图的大小、位置、对齐方式、内边距等，告诉视图如何在视图层级结构中排列自身。

## 概述

使用布局修饰符可以微调视图在视图层级结构中的位置。您可以调整或约束视图的大小、位置和对齐方式。您还可以为视图添加内边距，并指示视图如何与系统定义的安全区域交互。

要开始排列视图，请参阅 [Layout-fundamentals](Layout-fundamentals.zh-Hans.md)。要调整基本布局，请参阅 [Layout-adjustments](Layout-adjustments.zh-Hans.md)。

## 尺寸

- **frame(width:height:alignment:)**：将此视图放置在指定尺寸的不可见框架内。

- **frame(depth:alignment:)**：将此视图放置在指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图放置在具有指定尺寸约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图放置在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图放置在相对于最近容器的尺寸的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图放置在相对于最近容器的尺寸的不可见框架内。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图放置在相对于最近容器的尺寸的不可见框架内。

- **fixedSize()**：将此视图固定在理想尺寸。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想尺寸。

- **layoutPriority(_:)**：设置父布局分配给此子视图的空间优先级。

## 位置

- **position(_:)**：将此视图的中心定位到其父视图坐标空间中的指定点。

- **position(x:y:)**：将此视图的中心定位到其父视图坐标空间中的指定坐标。

- **offset(_:)**：将此视图水平和垂直偏移指定偏移量。

- **offset(x:y:)**：将此视图水平和垂直偏移指定距离。

- **offset(z:)**：将视图沿 Z 轴向前移动指定距离（以点为单位）。

- **coordinateSpace(_:)**：为视图的坐标空间指定一个名称，以便其他代码可以相对于该命名空间操作点和尺寸等尺寸。

## 对齐方式

- **alignmentGuide(_:computeValue:)**：设置视图的水平对齐方式。

## 内边距和间距

- **padding(_:)**：为该视图的每条边添加不同的内边距。

- **padding(_:_:)**：为该视图的特定边添加相等的内边距。

- **padding3D(_:)**：使用您指定的边内边距为该视图添加内边距。

- **padding3D(_:_:)**：使用您指定的边内边距为该视图添加内边距。

- **listRowInsets(_:)**：为列表中的行添加内边距。

- **scenePadding(_:)**：根据当前场景，为该视图的指定边缘添加合适的内边距。

- **scenePadding(_:edges:)**：根据当前场景，为该视图的指定边缘添加指定类型的内边距。

- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。

- **listSectionSpacing(_:)**：将 [List](List.zh-Hans.md) 中相邻部分之间的间距设置为自定义值。

## 网格配置

- **gridCellColumns(_:)**：指示作为网格单元格的视图跨越指定的列数。

- **gridCellAnchor(_:)**：为用作网格单元格的视图指定自定义对齐锚点。

- **gridCellUnsizedAxes(_:)**：要求网格布局不要在指定的轴上为视图提供额外的尺寸。

- **gridColumnAlignment(_:)**：覆盖视图所在网格列的默认水平对齐方式。

## 安全区域和边距

- **ignoresSafeArea(_:edges:)**：扩展视图的安全区域。

- **safeAreaInset(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容。

- **safeAreaPadding(_:)**：将提供的内边距添加到此视图的安全区域中。

- **safeAreaPadding(_:_:)**：将提供的内边距添加到此视图的安全区域中。

- **contentMargins(_:for:)**：配置指定位置的内容边距。

- **contentMargins(_:_:for:)**：配置指定位置的内容边距。

## 图层顺序

- **zIndex(_:)**：控制重叠视图的显示顺序。

## 布局方向

- **layoutDirectionBehavior(_:)**：设置此视图在不同布局方向上的行为。

## 自定义布局特性

- **layoutValue(key:value:)**：将值与自定义布局属性关联。

## 绘图视图

- **样式修改器**：将内置样式应用于不同类型的视图。

- **图形和渲染修改器**：影响系统绘制视图的方式，例如缩放或遮罩视图，或应用图形效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Layout
crawled: 2025-12-02T17:22:14Z
---

# Layout modifiers

**API Collection**

Tell a view how to arrange itself within a view hierarchy by adjusting its size, position, alignment, padding, and so on.

## Overview

Use layout modifiers to fine tune the placement of views in a view hierarchy. You can adjust or constrain the size, position, and alignment of a view. You can also add padding around a view, and indicate how the view interacts with system-defined safe areas.

To get started arranging views, see [Layout-fundamentals](Layout-fundamentals.zh-Hans.md). To make adjustments to a basic layout, see [Layout-adjustments](Layout-adjustments.zh-Hans.md).

## Size

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

## Position

- **position(_:)**: Positions the center of this view at the specified point in its parent’s coordinate space.
- **position(x:y:)**: Positions the center of this view at the specified coordinates in its parent’s coordinate space.
- **offset(_:)**: Offset this view by the horizontal and vertical amount specified in the offset parameter.
- **offset(x:y:)**: Offset this view by the specified horizontal and vertical distances.
- **offset(z:)**: Brings a view forward in Z by the provided distance in points.
- **coordinateSpace(_:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.

## Alignment

- **alignmentGuide(_:computeValue:)**: Sets the view’s horizontal alignment.

## Padding and spacing

- **padding(_:)**: Adds a different padding amount to each edge of this view.
- **padding(_:_:)**: Adds an equal padding amount to specific edges of this view.
- **padding3D(_:)**: Pads this view using the edge insets you specify.
- **padding3D(_:_:)**: Pads this view using the edge insets you specify.
- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **scenePadding(_:)**: Adds padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **scenePadding(_:edges:)**: Adds a specified kind of padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](List.zh-Hans.md) to a custom value.

## Grid configuration

- **gridCellColumns(_:)**: Tells a view that acts as a cell in a grid to span the specified number of columns.
- **gridCellAnchor(_:)**: Specifies a custom alignment anchor for a view that acts as a grid cell.
- **gridCellUnsizedAxes(_:)**: Asks grid layouts not to offer the view extra size in the specified axes.
- **gridColumnAlignment(_:)**: Overrides the default horizontal alignment of the grid column that the view appears in.

## Safe area and margins

- **ignoresSafeArea(_:edges:)**: Expands the safe area of a view.
- **safeAreaInset(edge:alignment:spacing:content:)**: Shows the specified content beside the modified view.
- **safeAreaPadding(_:)**: Adds the provided insets into the safe area of this view.
- **safeAreaPadding(_:_:)**: Adds the provided insets into the safe area of this view.
- **contentMargins(_:for:)**: Configures the content margin for a provided placement.
- **contentMargins(_:_:for:)**: Configures the content margin for a provided placement.

## Layer order

- **zIndex(_:)**: Controls the display order of overlapping views.

## Layout direction

- **layoutDirectionBehavior(_:)**: Sets the behavior of this view for different layout directions.

## Custom layout characteristics

- **layoutValue(key:value:)**: Associates a value with a custom layout property.

## Drawing views

- **Style modifiers**: Apply built-in styles to different types of views.
- **Graphics and rendering modifiers**: Affect the way the system draws a view, for example by scaling or masking a view, or by applying graphical effects.

