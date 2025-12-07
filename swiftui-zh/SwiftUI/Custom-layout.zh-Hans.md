---
来源： https://developer.apple.com/documentation/SwiftUI/Custom-layout
抓取时间： 2025-12-02T17:38:24Z
---

# 自定义布局

** 应用程序集**

在自定义布局中放置视图，并在布局类型之间创建动画过渡。

### 概览

您可以使用 SwiftUI 提供的内置布局容器和布局视图修改器创建复杂的视图布局。但是，如果您需要使用内置布局工具无法实现的行为，可使用[Layout](Layout.zh-Hans.md) 协议创建自定义布局容器类型。您定义的容器会询问其所有子视图的大小，然后指出在其自身范围内放置子视图的位置。



您还可以在符合[Layout](Layout.zh-Hans.md) 协议的布局类型（包括内置布局和自定义布局）之间创建动画过渡。

有关设计指导，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/layout]。

## 创建自定义布局容器

- 使用 SwiftUI 构建自定义布局**：使用 SwiftUI 提供的布局工具在应用程序的界面中排列视图。
- **Layout**：定义视图集合几何图形的类型。
- **LayoutSubview**：表示布局中一个子视图的代理。
- **LayoutSubviews**：表示布局视图的子视图的代理值集合。

## 配置自定义布局

- **LayoutProperties**：布局容器的特定布局属性。
- **ProposedViewSize**：视图大小的建议。
- **ViewSpacing**：视图的几何间距偏好集合。

## 在自定义布局中将值与视图关联起来

- **layoutValue(key:value:)**：将值与自定义布局属性关联。
- **LayoutValueKey**：用于访问布局容器子视图布局值的键。

## 在布局类型之间转换

- **AnyLayout**：布局协议的类型擦除实例。
- **HStackLayout**：水平容器，可在条件布局中使用。
- **VStackLayout**：垂直容器，可在条件布局中使用。
- **ZStackLayout**：重叠容器，可在条件布局中使用。
- **GridLayout**：可在条件布局中使用的网格。

## 查看布局

- **布局基础**：在堆栈和网格等内置布局容器内排列视图。
- **布局调整**：对齐方式、间距、填充和其他布局参数进行微调。
- **Lists**：显示结构化、可滚动的信息列。
- **Tables**：显示按行和列排列的可选择、可排序数据。
- **视图分组**：在不同类型的目的驱动容器（如表单或控件组）中显示视图。
- 滚动视图**：让用户可以滚动浏览当前显示屏无法显示的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/Custom-layout
crawled: 2025-12-02T17:38:24Z
---

# Custom layout

**API Collection**

Place views in custom arrangements and create animated transitions between layout types.

## Overview

You can create complex view layouts using the built-in layout containers and layout view modifiers that SwiftUI provides. However, if you need behavior that you can’t achieve with the built-in layout tools, create a custom layout container type using the [Layout](Layout.zh-Hans.md) protocol. A container that you define asks for the sizes of all its subviews, and then indicates where to place the subviews within its own bounds.



You can also create animated transitions among layout types that conform to the [Layout](Layout.zh-Hans.md) procotol, including both built-in and custom layouts.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/layout] in the Human Interface Guidelines.

## Creating a custom layout container

- **Composing custom layouts with SwiftUI**: Arrange views in your app’s interface using layout tools that SwiftUI provides.
- **Layout**: A type that defines the geometry of a collection of views.
- **LayoutSubview**: A proxy that represents one subview of a layout.
- **LayoutSubviews**: A collection of proxy values that represent the subviews of a layout view.

## Configuring a custom layout

- **LayoutProperties**: Layout-specific properties of a layout container.
- **ProposedViewSize**: A proposal for the size of a view.
- **ViewSpacing**: A collection of the geometric spacing preferences of a view.

## Associating values with views in a custom layout

- **layoutValue(key:value:)**: Associates a value with a custom layout property.
- **LayoutValueKey**: A key for accessing a layout value of a layout container’s subviews.

## Transitioning between layout types

- **AnyLayout**: A type-erased instance of the layout protocol.
- **HStackLayout**: A horizontal container that you can use in conditional layouts.
- **VStackLayout**: A vertical container that you can use in conditional layouts.
- **ZStackLayout**: An overlaying container that you can use in conditional layouts.
- **GridLayout**: A grid that you can use in conditional layouts.

## View layout

- **Layout fundamentals**: Arrange views inside built-in layout containers like stacks and grids.
- **Layout adjustments**: Make fine adjustments to alignment, spacing, padding, and other layout parameters.
- **Lists**: Display a structured, scrollable column of information.
- **Tables**: Display selectable, sortable data arranged in rows and columns.
- **View groupings**: Present views in different kinds of purpose-driven containers, like forms or control groups.
- **Scroll views**: Enable people to scroll to content that doesn’t fit in the current display.

