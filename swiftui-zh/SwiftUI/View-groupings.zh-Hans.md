---
来源： https://developer.apple.com/documentation/SwiftUI/View-groupings
抓取时间： 2025-12-02T17:38:26Z
---

# 查看分组

** 应用程序集**

在不同类型的目的驱动容器（如表单或控件组）中展示视图。

### 概览

你可以创建不同用途的视图组。



例如，[Group](Group.zh-Hans.md) 结构会将指定的视图视为一个单元，而不会施加任何额外的布局或外观特征。一个[Form](Form.zh-Hans.md)结构会呈现一组具有特定平台外观的元素，适合收集人们的意见。

有关设计指导，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/layout]。

## 将视图分组到容器中

- 创建自定义容器视图**：访问单个子视图以组成灵活的容器视图。
- **Group**：将内容类型（如视图、场景或命令）的多个实例集合为一个单元的类型。
- **GroupElementsOfContent**：将给定视图的子视图转化为结果内容视图。
- **GroupSectionsOfContent**：将给定视图的分区转换为结果内容视图。

## 将视图组织成部分

- **Section**：容器视图，可用于在某些视图中添加层次结构。
- **SectionCollection**：表示视图部分的不透明集合。
- **SectionConfiguration**：指定部分的内容。

## 对动态数据进行迭代

- **ForEach**：一种结构，可根据需要从标识数据的底层集合中计算视图。
- **ForEachSectionCollection**：一种集合，允许在 for each 循环中将视图视为其部分的集合。
- **ForEachSubviewCollection**：允许在 for each 循环中将视图视为其子视图集合的集合。
- **DynamicViewContent**：一种视图类型，可从底层数据集合生成视图。

## 访问容器的子视图

- **Subview**：表示另一个视图的子视图的不透明值。
- **SubviewsCollection**：表示视图子视图的不透明集合。
- **SubviewsCollectionSlice**：SubviewsCollection 的一个片段。
- **containerValue(_:_:)**：设置视图的特定容器值。
- **ContainerValues**：与给定视图关联的容器值的集合。
- **ContainerValueKey**：用于访问容器值的键。

## 将视图分组到一个框中

- **GroupBox**：一种风格化视图，带有可选标签，可直观地将内容进行逻辑分组。
- **groupBoxStyle(_:)**：为该视图中的分组框设置样式。

## 分组输入

- **Form**：用于分组数据输入控件的容器，如设置或检查器中的控件。
- **formStyle(_:)**：为视图层次结构中的表单设置样式。
- **LabeledContent**：用于将标签附加到带值视图的容器。
- **labeledContentStyle(_:)**：为标签内容设置样式。

## 呈现一组控件

- **ControlGroup**：一个容器视图，以适合上下文的视觉方式显示语义相关的控件
- **controlGroupStyle(_:)**：设置该视图中控件组的样式。

### 视图布局

- **布局基础**：在堆栈和网格等内置布局容器内排列视图。
- **布局调整**：对齐方式、间距、填充和其他布局参数进行微调。
- 自定义布局**：将视图置于自定义布局中，并在布局类型之间创建动画过渡。
- **Lists**：显示结构化、可滚动的信息列。
- **Tables**：显示按行和列排列的可选择、可排序数据。
- 滚动视图**：让用户可以滚动浏览当前显示屏无法显示的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View-groupings
crawled: 2025-12-02T17:38:26Z
---

# View groupings

**API Collection**

Present views in different kinds of purpose-driven containers, like forms or control groups.

## Overview

You can create groups of views that serve different purposes.



For example, a [Group](Group.zh-Hans.md) construct treats the specified views as a unit without imposing any additional layout or appearance characteristics. A [Form](Form.zh-Hans.md) presents a group of elements with a platform-specific appearance that’s suitable for gathering input from people.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/layout] in the Human Interface Guidelines.

## Grouping views into a container

- **Creating custom container views**: Access individual subviews to compose flexible container views.
- **Group**: A type that collects multiple instances of a content type — like views, scenes, or commands — into a single unit.
- **GroupElementsOfContent**: Transforms the subviews of a given view into a resulting content view.
- **GroupSectionsOfContent**: Transforms the sections of a given view into a resulting content view.

## Organizing views into sections

- **Section**: A container view that you can use to add hierarchy within certain views.
- **SectionCollection**: An opaque collection representing the sections of view.
- **SectionConfiguration**: Specifies the contents of a section.

## Iterating over dynamic data

- **ForEach**: A structure that computes views on demand from an underlying collection of identified data.
- **ForEachSectionCollection**: A collection which allows a view to be treated as a collection of its sections in a for each loop.
- **ForEachSubviewCollection**: A collection which allows a view to be treated as a collection of its subviews in a for each loop.
- **DynamicViewContent**: A type of view that generates views from an underlying collection of data.

## Accessing a container’s subviews

- **Subview**: An opaque value representing a subview of another view.
- **SubviewsCollection**: An opaque collection representing the subviews of view.
- **SubviewsCollectionSlice**: A slice of a SubviewsCollection.
- **containerValue(_:_:)**: Sets a particular container value of a view.
- **ContainerValues**: A collection of container values associated with a given view.
- **ContainerValueKey**: A key for accessing container values.

## Grouping views into a box

- **GroupBox**: A stylized view, with an optional label, that visually collects a logical grouping of content.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.

## Grouping inputs

- **Form**: A container for grouping controls used for data entry, such as in settings or inspectors.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **LabeledContent**: A container for attaching a label to a value-bearing view.
- **labeledContentStyle(_:)**: Sets a style for labeled content.

## Presenting a group of controls

- **ControlGroup**: A container view that displays semantically-related controls in a visually-appropriate manner for the context
- **controlGroupStyle(_:)**: Sets the style for control groups within this view.

## View layout

- **Layout fundamentals**: Arrange views inside built-in layout containers like stacks and grids.
- **Layout adjustments**: Make fine adjustments to alignment, spacing, padding, and other layout parameters.
- **Custom layout**: Place views in custom arrangements and create animated transitions between layout types.
- **Lists**: Display a structured, scrollable column of information.
- **Tables**: Display selectable, sortable data arranged in rows and columns.
- **Scroll views**: Enable people to scroll to content that doesn’t fit in the current display.

