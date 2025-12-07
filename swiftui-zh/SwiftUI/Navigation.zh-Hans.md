--- 来源：https://developer.apple.com/documentation/SwiftUI/Navigation
抓取时间：2025-12-02T17:20:45Z

---

# 导航

**API 集合**

使用户能够在场景内，在应用视图层级结构的不同部分之间轻松切换。

## 概述

使用导航容器为应用的用户界面构建结构，使用户能够轻松地在应用的各个部分之间切换。

例如，用户可以使用 [NavigationStack](NavigationStack.zh-Hans.md) 在视图堆栈中前后移动，或者使用 [TabView](TabView.zh-Hans.md) 从标签栏中选择要显示的视图。

通过向容器添加视图修饰符（例如 [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md)）来配置导航容器。使用容器内视图的其他修饰符来影响容器在显示该视图时的行为。例如，您可以在视图上使用 [navigationTitle(_:)](View/navigationTitle.zh-Hans.md) 来提供工具栏标题，以便在显示该视图时显示。

## 基础知识

- **理解导航堆栈**：了解导航堆栈、链接以及如何在应用程序结构中管理导航类型。

## 以列形式呈现视图

- **为您的 SwiftUI 应用构建强大的导航结构**：使用导航链接、堆栈、目标和路径，为所有平台提供流畅的体验，以及深度链接和状态恢复等功能。

- **迁移到新的导航类型**：通过将导航视图替换为导航堆栈和导航拆分视图，改进应用程序中的导航行为。

- **NavigationSplitView**：以两列或三列形式呈现视图的视图，其中前几列中的选择控制后续列的呈现方式。

- **navigationSplitViewStyle(_:)**：设置此视图中导航拆分视图的样式。

- **navigationSplitViewColumnWidth(_:)**：设置包含此视图的列的固定首选宽度。

- **navigationSplitViewColumnWidth(min:ideal:max:)**：设置包含此视图的列的灵活首选宽度。

- **NavigationSplitViewVisibility**：导航拆分视图中前导列的可见性。

- **NavigationLink**：控制导航呈现方式的视图。

## 在同一列中堆叠视图

- **NavigationStack**：显示根视图并允许您在根视图之上显示其他视图的视图。

- **NavigationPath**：表示导航堆栈内容的已擦除类型的数据列表。

- **navigationDestination(for:destination:)**：将目标视图与在导航堆栈中使用的呈现数据类型关联起来。

- **navigationDestination(isPresented:destination:)**：将目标视图与一个绑定关联起来，该绑定可用于将视图推送到 [NavigationStack](NavigationStack.zh-Hans.md)。

- **navigationDestination(item:destination:)**：将目标视图与一个绑定值关联起来，以便在导航堆栈或导航拆分视图中使用。

## 管理列折叠

- **NavigationSplitViewColumn**：表示导航拆分视图中一列的视图。

## 设置导航内容的标题

- **navigationTitle(_:)**：使用字符串绑定配置视图的导航标题。

- **navigationSubtitle(_:)**：配置视图的导航副标题。

- **navigationDocument(_:)**：配置视图的导航文档。

- **navigationDocument(_:preview:)**：配置视图的文档，以便进行导航。

## 配置导航栏

- **navigationBarBackButtonHidden(_:)**：隐藏视图的导航栏返回按钮。

- **navigationBarTitleDisplayMode(_:)**：配置此视图的标题显示模式。

- **NavigationBarItem**：位于导航堆栈顶部的视图的导航栏配置。

## 配置侧边栏

- **sidebarRowSize**：侧边栏行的当前大小。

- **SidebarRowSize**：侧边栏行的标准大小。

## 以标签页形式呈现视图

- **使用标签页导航增强应用内容**：将应用内容置于中心位置，同时使用标签页快速访问导航。

- **TabView**：使用交互式用户界面元素在多个子视图之间切换的视图。

- **Tab**：选项卡视图中选项卡的内容及其关联的选项卡项。

- **TabRole**：定义选项卡用途的值。

- **TabSection**：可用于在选项卡视图中添加层级结构的容器。

- **tabViewStyle(_:)**：设置当前环境中选项卡视图的样式。

## 配置选项卡栏

- **defaultAdaptableTabBarPlacement(_:)**：使用自适应侧边栏样式指定选项卡视图中选项卡的默认位置。

- **tabViewSidebarHeader(content:)**：向选项卡视图的侧边栏添加自定义标题。

- **tabViewSidebarFooter(content:)**：为标签视图的侧边栏添加自定义页脚。

- **tabViewSidebarBottomBar(content:)**：为标签视图的侧边栏添加自定义底部栏。

- **AdaptableTabBarPlacement**：使用自适应侧边栏样式时，标签在标签视图中的位置。

- **tabBarPlacement**：标签栏的当前位置。

- **TabBarPlacement**：标签在标签视图中的位置。

- **isTabBarShowingSections**：一个布尔值，用于确定标签视图是否显示标签部分的展开内容。

- **TabBarMinimizeBehavior**

- **TabViewBottomAccessoryPlacement**：标签视图中底部附件的位置。您可以根据位置调整附件视图的内容。

## 配置选项卡

- **sectionActions(content:)**：为选项卡添加自定义操作。

- **TabPlacement**：选项卡的显示位置。

- **TabContentBuilder**：用于构建支持程序化选择的选项卡视图的选项卡的结果生成器。此生成器要求选项卡视图中的所有选项卡具有相同的选择类型。

- **TabContent**：为选项卡视图中可通过程序选择的选项卡提供内容的类型。

- **AnyTabContent**：擦除选项卡内容的类型。

## 启用选项卡自定义

- **tabViewCustomization(_:)**：指定要应用于选项卡视图侧边栏表示的自定义设置。

- **TabViewCustomization**：用户对可自适应侧边栏选项卡视图所做的自定义设置。

- **TabCustomizationBehavior**：可自定义标签视图内容的自定义行为。

## 在多个窗格中显示视图

- **HSplitView**：一种布局容器，它将子视图水平排列，并允许用户使用分隔符调整其大小。

- **VSplitView**：一种布局容器，它将子视图垂直排列，并允许用户使用分隔符调整其大小。

## 已弃用类型

- **NavigationView**：用于呈现视图堆栈的视图，该堆栈表示导航层次结构中的可见路径。

- **tabItem(_:)**：设置与此视图关联的标签栏项。

## 应用结构

- **应用组织结构**：定义应用的入口点和顶级结构。

- **Scenes**：声明构成应用程序各个部分的用户界面分组。

- **Windows**：在单个窗口或窗口集合中显示用户界面内容。

- **沉浸式空间**：在用户的周围环境中显示无边界的内容。

- **Documents**：允许用户打开和管理文档。

- **模态呈现**：在提供专注交互的独立视图中呈现内容。

- **Toolbars**：提供对常用命令和控件的快速访问。

- **Search**：允许用户在应用程序内搜索文本或其他内容。

- **应用程序扩展**：将应用程序的基本功能扩展到系统的其他部分，例如通过添加小部件。


---
source: https://developer.apple.com/documentation/SwiftUI/Navigation
crawled: 2025-12-02T17:20:45Z
---

# Navigation

**API Collection**

Enable people to move between different parts of your app’s view hierarchy within a scene.

## Overview

Use navigation containers to provide structure to your app’s user interface, enabling people to easily move among the parts of your app.



For example, people can move forward and backward through a stack of views using a [NavigationStack](NavigationStack.zh-Hans.md), or choose which view to display from a tab bar using a [TabView](TabView.zh-Hans.md).

Configure navigation containers by adding view modifiers like [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md) to the container. Use other modifiers on the views inside the container to affect the container’s behavior when showing that view. For example, you can use [navigationTitle(_:)](View/navigationTitle.zh-Hans.md) on a view to provide a toolbar title to display when showing that view.

## Essentials

- **Understanding the navigation stack**: Learn about the navigation stack, links, and how to manage navigation types in your app’s structure.

## Presenting views in columns

- **Bringing robust navigation structure to your SwiftUI app**: Use navigation links, stacks, destinations, and paths to provide a streamlined experience for all platforms, as well as behaviors such as deep linking and state restoration.
- **Migrating to new navigation types**: Improve navigation behavior in your app by replacing navigation views with navigation stacks and navigation split views.
- **NavigationSplitView**: A view that presents views in two or three columns, where selections in leading columns control presentations in subsequent columns.
- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.
- **NavigationSplitViewVisibility**: The visibility of the leading columns in a navigation split view.
- **NavigationLink**: A view that controls a navigation presentation.

## Stacking views in one column

- **NavigationStack**: A view that displays a root view and enables you to present additional views over the root view.
- **NavigationPath**: A type-erased list of data representing the content of a navigation stack.
- **navigationDestination(for:destination:)**: Associates a destination view with a presented data type for use within a navigation stack.
- **navigationDestination(isPresented:destination:)**: Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](NavigationStack.zh-Hans.md).
- **navigationDestination(item:destination:)**: Associates a destination view with a bound value for use within a navigation stack or navigation split view

## Managing column collapse

- **NavigationSplitViewColumn**: A view that represents a column in a navigation split view.

## Setting titles for navigation content

- **navigationTitle(_:)**: Configures the view’s title for purposes of navigation, using a string binding.
- **navigationSubtitle(_:)**: Configures the view’s subtitle for purposes of navigation.
- **navigationDocument(_:)**: Configures the view’s document for purposes of navigation.
- **navigationDocument(_:preview:)**: Configures the view’s document for purposes of navigation.

## Configuring the navigation bar

- **navigationBarBackButtonHidden(_:)**: Hides the navigation bar back button for the view.
- **navigationBarTitleDisplayMode(_:)**: Configures the title display mode for this view.
- **NavigationBarItem**: A configuration for a navigation bar that represents a view at the top of a navigation stack.

## Configuring the sidebar

- **sidebarRowSize**: The current size of sidebar rows.
- **SidebarRowSize**: The standard sizes of sidebar rows.

## Presenting views in tabs

- **Enhancing your app’s content with tab navigation**: Keep your app content front and center while providing quick access to navigation using the tab bar.
- **TabView**: A view that switches between multiple child views using interactive user interface elements.
- **Tab**: The content for a tab and the tab’s associated tab item in a tab view.
- **TabRole**: A value that defines the purpose of the tab.
- **TabSection**: A container that you can use to add hierarchy within a tab view.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **tabBarPlacement**: The current placement of the tab bar.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

## Configuring a tab

- **sectionActions(content:)**: Adds custom actions to a section.
- **TabPlacement**: A place that a tab can appear.
- **TabContentBuilder**: A result builder that constructs tabs for a tab view that supports programmatic selection. This builder requires that all tabs in the tab view have the same selection type.
- **TabContent**: A type that provides content for programmatically selectable tabs in a tab view.
- **AnyTabContent**: Type erased tab content.

## Enabling tab customization

- **tabViewCustomization(_:)**: Specifies the customizations to apply to the sidebar representation of the tab view.
- **TabViewCustomization**: The customizations a person makes to an adaptable sidebar tab view.
- **TabCustomizationBehavior**: The customization behavior of customizable tab view content.

## Displaying views in multiple panes

- **HSplitView**: A layout container that arranges its children in a horizontal line and allows the user to resize them using dividers placed between them.
- **VSplitView**: A layout container that arranges its children in a vertical line and allows the user to resize them using dividers placed between them.

## Deprecated Types

- **NavigationView**: A view for presenting a stack of views that represents a visible path in a navigation hierarchy.
- **tabItem(_:)**: Sets the tab bar item associated with this view.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

