--- 来源：https://developer.apple.com/documentation/SwiftUI/Lists

抓取时间：2025-12-02T17:38:25Z

---

# 列表

**API 集合**

显示结构化的、可滚动的信息列。

## 概述

使用列表显示一维垂直视图集合。

列表是一种复杂的容器类型，当其大小超出当前显示范围时，会自动提供滚动功能。您可以通过为列表中的每一行提供单独的视图来构建列表，也可以使用 [ForEach](ForEach.zh-Hans.md) 枚举一组行。您还可以混合使用这些策略，将任意数量的单独视图和 `ForEach` 构造组合在一起。

使用视图修饰符来配置列表及其行、标题、部分和分隔符的外观和行为。例如，您可以为列表应用样式，为单个行添加滑动操作，或使列表可通过下拉手势刷新。您还可以使用与 [Scroll-views](Scroll-views.zh-Hans.md) 关联的配置来控制列表的隐式滚动行为。

有关设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/lists-and-tables]。

## 创建列表

- **在列表中显示数据**：以适合平台的外观可视化数据集合。

- **List**：一个容器，用于以单列形式呈现数据行，并可选择是否提供选择一个或多个成员的功能。

- **listStyle(_:)**：设置此视图中列表的样式。

## 逐步披露信息

- **OutlineGroup**：一种结构，可根据底层树状结构化的已识别数据集合按需计算视图和披露组。

- **DisclosureGroup**：一种视图，可根据披露控件的状态显示或隐藏其他内容视图。

- **disclosureGroupStyle(_:)**：设置此视图中披露组的样式。

## 配置列表布局

- **listRowInsets(_:)**：为列表中的行应用内边距。

- **defaultMinListRowHeight**：列表中行的默认最小高度。

- **defaultMinListHeaderHeight**：列表中标题的默认最小高度。

- **listRowSpacing(_:)**：设置列表中相邻两行之间的垂直间距。

- **listSectionSpacing(_:)**：设置列表 [List](List.zh-Hans.md) 中相邻部分之间的间距为自定义值。

- **ListSectionSpacing**：设置列表中两个相邻部分之间的间距选项。

- **listSectionMargins(_:_:)**：设置特定边缘的节边距。

## 配置行

- **listItemTint(_:)**：设置列表中内容的固定色调颜色。

- **ListItemTint**：可应用于列表中内容的色调效果配置。

## 配置标题

- **headerProminence(_:)**：设置此视图的标题突出显示级别。

- **headerProminence**：应用于视图中节标题的突出显示级别。

- **Prominence**：用于指示视图层级结构重要性的类型。

## 配置分隔符

- **listRowSeparatorTint(_:edges:)**：设置与行关联的色调颜色。

- **listSectionSeparatorTint(_:edges:)**：设置与节关联的色调颜色。

- **listRowSeparator(_:edges:)**：设置与此特定行关联的分隔符的显示模式。

- **listSectionSeparator(_:edges:)**：设置是否隐藏与列表节关联的分隔符。

## 配置背景

- **listRowBackground(_:)**：在列表行项后放置自定义背景视图。

- **alternatingRowBackgrounds(_:)**：覆盖此视图中的列表和表格是否具有交替的行背景。

- **AlternatingRowBackgroundBehavior**：视图的样式，用于设置交替行背景。

- **backgroundProminence**：与此环境关联的视图下方背景的突出显示程度。

- **BackgroundProminence**：其他视图下方背景的突出显示程度。

## 在列表项上显示徽章

- **badge(_:)**：根据整数值生成视图的徽章。

- **badgeProminence(_:)**：指定此视图创建的徽章的突出显示程度。

- **badgeProminence**：应用于与此环境关联的徽章的突出显示程度。

- **BadgeProminence**：徽章的视觉突出显示程度。

## 配置交互

- **swipeActions(edge:allowsFullSwipe:content:)**：为列表中的某一行添加自定义滑动操作。

- **selectionDisabled(_:)**：添加一个条件，用于控制用户是否可以选择此视图。

- **listRowHoverEffect(_:)**：请求包含该行的列表行使用提供的悬停效果。

- **listRowHoverEffectDisabled(_:)**：请求禁用包含该行的列表行的悬停效果。

## 刷新列表内容

- **refreshable(action:)**：将此视图标记为可刷新。

- **refresh**：存储在视图环境中的刷新操作。

- **RefreshAction**：启动刷新操作的操作。

## 编辑列表

- **moveDisabled(_:)**：添加一个条件，用于判断视图的层级结构是否可移动。

- **deleteDisabled(_:)**：添加一个条件，用于判断视图的层级结构是否可删除。

- **editMode**：指示用户是否可以编辑与此环境关联的视图的内容。

- **EditMode**：指示用户是否可以编辑视图内容的模式。

- **EditActions**：一组视图可以向用户提供的、针对数据集合的编辑操作。

- **EditableCollectionContent**：一个不透明的包装视图，用于为列表中的行添加编辑功能。

- **IndexedIdentifierCollection**：一个集合包装器，用于遍历集合的索引和标识符。

## 配置节索引

- **listSectionIndexVisibility(_:)**：更改列表节索引的可见性。

- **sectionIndexLabel(_:)**：设置节索引中使用的标签，使其指向当前节，通常只有一个字符。

## 视图布局

- **布局基础**：在内置布局容器（例如堆栈和网格）中排列视图。

- **布局调整**：对对齐方式、间距、内边距和其他布局参数进行微调。

- **自定义布局**：以自定义方式放置视图，并在布局类型之间创建动画过渡效果。

- **Tables**：以行和列的形式显示可选择、可排序的数据。

- **视图分组**：将视图呈现在不同类型的、用途各异的容器中，例如表单或控件组。

- **滚动视图**：允许用户滚动查看当前显示区域之外的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Lists
crawled: 2025-12-02T17:38:25Z
---

# Lists

**API Collection**

Display a structured, scrollable column of information.

## Overview

Use a list to display a one-dimensional vertical collection of views.



The list is a complex container type that automatically provides scrolling when it grows too large for the current display. You build a list by providing it with individual views for the rows in the list, or by using a [ForEach](ForEach.zh-Hans.md) to enumerate a group of rows. You can also mix these strategies, blending any number of individual views and `ForEach` constructs.

Use view modifiers to configure the appearance and behavior of a list and its rows, headers, sections, and separators. For example, you can apply a style to the list, add swipe gestures to individual rows, or make the list refreshable with a pull-down gesture. You can also use the configuration associated with [Scroll-views](Scroll-views.zh-Hans.md) to control the list’s implicit scrolling behavior.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/lists-and-tables] in the Human Interface Guidelines.

## Creating a list

- **Displaying data in lists**: Visualize collections of data with platform-appropriate appearance.
- **List**: A container that presents rows of data arranged in a single column, optionally providing the ability to select one or more members.
- **listStyle(_:)**: Sets the style for lists within this view.

## Disclosing information progressively

- **OutlineGroup**: A structure that computes views and disclosure groups on demand from an underlying collection of tree-structured, identified data.
- **DisclosureGroup**: A view that shows or hides another content view, based on the state of a disclosure control.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.

## Configuring a list’s layout

- **listRowInsets(_:)**: Applies an inset to the rows in a list.
- **defaultMinListRowHeight**: The default minimum height of rows in a list.
- **defaultMinListHeaderHeight**: The default minimum height of a header in a list.
- **listRowSpacing(_:)**: Sets the vertical spacing between two adjacent rows in a List.
- **listSectionSpacing(_:)**: Sets the spacing between adjacent sections in a [List](List.zh-Hans.md) to a custom value.
- **ListSectionSpacing**: The spacing options between two adjacent sections in a list.
- **listSectionMargins(_:_:)**: Set the section margins for the specific edges.

## Configuring rows

- **listItemTint(_:)**: Sets a fixed tint color for content in a list.
- **ListItemTint**: A tint effect configuration that you can apply to content in a list.

## Configuring headers

- **headerProminence(_:)**: Sets the header prominence for this view.
- **headerProminence**: The prominence to apply to section headers within a view.
- **Prominence**: A type indicating the prominence of a view hierarchy.

## Configuring separators

- **listRowSeparatorTint(_:edges:)**: Sets the tint color associated with a row.
- **listSectionSeparatorTint(_:edges:)**: Sets the tint color associated with a section.
- **listRowSeparator(_:edges:)**: Sets the display mode for the separator associated with this specific row.
- **listSectionSeparator(_:edges:)**: Sets whether to hide the separator associated with a list section.

## Configuring backgrounds

- **listRowBackground(_:)**: Places a custom background view behind a list row item.
- **alternatingRowBackgrounds(_:)**: Overrides whether lists and tables in this view have alternating row backgrounds.
- **AlternatingRowBackgroundBehavior**: The styling of views with respect to alternating row backgrounds.
- **backgroundProminence**: The prominence of the background underneath views associated with this environment.
- **BackgroundProminence**: The prominence of backgrounds underneath other views.

## Displaying a badge on a list item

- **badge(_:)**: Generates a badge for the view from an integer value.
- **badgeProminence(_:)**: Specifies the prominence of badges created by this view.
- **badgeProminence**: The prominence to apply to badges associated with this environment.
- **BadgeProminence**: The visual prominence of a badge.

## Configuring interaction

- **swipeActions(edge:allowsFullSwipe:content:)**: Adds custom swipe actions to a row in a list.
- **selectionDisabled(_:)**: Adds a condition that controls whether users can select this view.
- **listRowHoverEffect(_:)**: Requests that the containing list row use the provided hover effect.
- **listRowHoverEffectDisabled(_:)**: Requests that the containing list row have its hover effect disabled.

## Refreshing a list’s content

- **refreshable(action:)**: Marks this view as refreshable.
- **refresh**: A refresh action stored in a view’s environment.
- **RefreshAction**: An action that initiates a refresh operation.

## Editing a list

- **moveDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is movable.
- **deleteDisabled(_:)**: Adds a condition for whether the view’s view hierarchy is deletable.
- **editMode**: An indication of whether the user can edit the contents of a view associated with this environment.
- **EditMode**: A mode that indicates whether the user can edit a view’s content.
- **EditActions**: A set of edit actions on a collection of data that a view can offer to a user.
- **EditableCollectionContent**: An opaque wrapper view that adds editing capabilities to a row in a list.
- **IndexedIdentifierCollection**: A collection wrapper that iterates over the indices and identifiers of a collection together.

## Configuring a section index

- **listSectionIndexVisibility(_:)**: Changes the visibility of the list section index.
- **sectionIndexLabel(_:)**: Sets the label that is used in a section index to point to this section, typically only a single character long.

## View layout

- **Layout fundamentals**: Arrange views inside built-in layout containers like stacks and grids.
- **Layout adjustments**: Make fine adjustments to alignment, spacing, padding, and other layout parameters.
- **Custom layout**: Place views in custom arrangements and create animated transitions between layout types.
- **Tables**: Display selectable, sortable data arranged in rows and columns.
- **View groupings**: Present views in different kinds of purpose-driven containers, like forms or control groups.
- **Scroll views**: Enable people to scroll to content that doesn’t fit in the current display.

