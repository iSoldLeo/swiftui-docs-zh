---

来源：https://developer.apple.com/documentation/SwiftUI/Tables
抓取时间：2025-12-02T17:38:26Z

---

# 表格

**API 集合**

以行和列的形式显示可选择、可排序的数据。

## 概述

使用表格来显示一组元素的多个值。集合中的每个元素都显示在表格的不同行中，而给定元素的每个值都显示在不同的列中。窄屏显示可能会自动调整，仅显示表格的第一列。

创建表格时，您需要提供一个元素集合，然后告诉表格如何查找每列所需的值。在简单情况下，SwiftUI 会推断每一行的元素，但在更复杂的场景中，您也可以显式指定行元素。通过少量额外的配置，您还可以使表格中的项目可选择，并使列可排序。

与 [List](List.zh-Hans.md) 类似，表格包含隐式垂直滚动，您可以使用 [Scroll-views](Scroll-views.zh-Hans.md) 中描述的视图修饰符进行配置。有关设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/lists-and-tables]。

## 创建表格

- **使用 SwiftUI 构建出色的 Mac 应用**：通过集成侧边栏、表格、工具栏和其他一些常用的用户界面元素，创建引人入胜的 SwiftUI Mac 应用。

- **Table**：一个容器，用于呈现排列成一列或多列的数据行，并可选择是否提供选择一个或多个成员的功能。

- **tableStyle(_:)**：设置此视图中表格的样式。

## 创建列

- **TableColumn**：一个列，用于显示表格中每一行的视图。

- **TableColumnContent**：用于表示表中的列的类型。

- **TableColumnAlignment**：描述表列内容的对齐方式。

- **TableColumnBuilder**：一个结果构建器，用于从闭包创建表列内容。

- **TableColumnForEach**：一个结构，用于根据底层已识别数据集合按需计算列。

## 自定义列

- **tableColumnHeaders(_:)**：控制 `Table` 列标题视图的可见性。

- **TableColumnCustomization**：表示表中列的状态。

- **TableColumnCustomizationBehavior**：表可以向用户提供的一组列自定义行为。

## 创建行

- **TableRow**：表示表格中数据值的行。

- **TableRowContent**：用于表示表格行的类型。

- **TableHeaderRowContent**：显示单列视图而非列式内容的表格行。

- **TupleTableRowContent**：一种表格列内容类型，它根据 Swift 表格行元组创建表格行。

- **TableForEachContent**：一种表格行内容类型，它通过遍历集合创建表格行。

- **EmptyTableRowContent**：不生成任何行的表格行内容。

- **DynamicTableRowContent**：一种表格行内容类型，它根据底层数据集合生成表格行。

- **TableRowBuilder**：一个结果构建器，用于根据闭包创建表格行内容。

## 添加渐进式披露

- **DisclosureTableRow**：一种表格行类型，可根据披露控件的状态显示或隐藏其他行。

- **TableOutlineGroupContent**：一种由表格的层次结构初始化器创建的不透明表格行类型。

## 视图布局

- **布局基础**：在内置布局容器（例如堆栈和网格）中排列视图。

- **布局调整**：对对齐方式、间距、内边距和其他布局参数进行微调。

- **自定义布局**：以自定义方式放置视图，并在布局类型之间创建动画过渡效果。

- **Lists**：显示结构化的、可滚动的信息列。

- **视图分组**：将视图呈现在不同类型的、用途各异的容器中，例如表单或控件组。

- **滚动视图**：允许用户滚动查看当前显示区域之外的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Tables
crawled: 2025-12-02T17:38:26Z
---

# Tables

**API Collection**

Display selectable, sortable data arranged in rows and columns.

## Overview

Use a table to display multiple values across a collection of elements. Each element in the collection appears in a different row of the table, while each value for a given element appears in a different column. Narrow displays may adapt to show only the first column of the table.



When you create a table, you provide a collection of elements, and then tell the table how to find the needed value for each column. In simple cases, SwiftUI infers the element for each row, but you can also specify the row elements explicitly in more complex scenarios. With a small amount of additional configuration, you can also make the items in the table selectable, and the columns sortable.

Like a [List](List.zh-Hans.md), a table includes implicit vertical scrolling that you can configure using the view modifiers described in [Scroll-views](Scroll-views.zh-Hans.md). For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/lists-and-tables] in the Human Interface Guidelines.

## Creating a table

- **Building a great Mac app with SwiftUI**: Create engaging SwiftUI Mac apps by incorporating side bars, tables, toolbars, and several other popular user interface elements.
- **Table**: A container that presents rows of data arranged in one or more columns, optionally providing the ability to select one or more members.
- **tableStyle(_:)**: Sets the style for tables within this view.

## Creating columns

- **TableColumn**: A column that displays a view for each row in a table.
- **TableColumnContent**: A type used to represent columns within a table.
- **TableColumnAlignment**: Describes the alignment of the content of a table column.
- **TableColumnBuilder**: A result builder that creates table column content from closures.
- **TableColumnForEach**: A structure that computes columns on demand from an underlying collection of identified data.

## Customizing columns

- **tableColumnHeaders(_:)**: Controls the visibility of a `Table`’s column header views.
- **TableColumnCustomization**: A representation of the state of the columns in a table.
- **TableColumnCustomizationBehavior**: A set of customization behaviors of a column that a table can offer to a user.

## Creating rows

- **TableRow**: A row that represents a data value in a table.
- **TableRowContent**: A type used to represent table rows.
- **TableHeaderRowContent**: A table row that displays a single view instead of columned content.
- **TupleTableRowContent**: A type of table column content that creates table rows created from a Swift tuple of table rows.
- **TableForEachContent**: A type of table row content that creates table rows created by iterating over a collection.
- **EmptyTableRowContent**: A table row content that doesn’t produce any rows.
- **DynamicTableRowContent**: A type of table row content that generates table rows from an underlying collection of data.
- **TableRowBuilder**: A result builder that creates table row content from closures.

## Adding progressive disclosure

- **DisclosureTableRow**: A kind of table row that shows or hides additional rows based on the state of a disclosure control.
- **TableOutlineGroupContent**: An opaque table row type created by a table’s hierarchical initializers.

## View layout

- **Layout fundamentals**: Arrange views inside built-in layout containers like stacks and grids.
- **Layout adjustments**: Make fine adjustments to alignment, spacing, padding, and other layout parameters.
- **Custom layout**: Place views in custom arrangements and create animated transitions between layout types.
- **Lists**: Display a structured, scrollable column of information.
- **View groupings**: Present views in different kinds of purpose-driven containers, like forms or control groups.
- **Scroll views**: Enable people to scroll to content that doesn’t fit in the current display.

