---
来源： https://developer.apple.com/documentation/SwiftUI/Toolbars
抓取时间： 2025-12-02T17:20:46Z
---

# 工具栏

** 应用程序集**

提供对常用命令和控件的即时访问。

## 概览

根据平台和上下文的不同，系统可能会在应用程序内容的上方或下方显示工具栏。



将[toolbar(content:)](View/toolbar_content.zh-Hans.md) 视图修饰符应用到应用程序的视图中，即可将项目添加到工具栏。您还可以使用视图修饰符配置工具栏。例如，您可以使用[toolbar(_:for:)](View/toolbar___for.zh-Hans.md)修饰符设置工具栏的可见性。

有关设计指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/toolbars]。

## 填充工具栏

- **toolbar(content:)**：用指定的项目填充工具栏或导航栏。
- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。
- **ToolbarItemGroup**：表示一组`ToolbarItem`的模型，可放置在工具栏或导航栏中。
- **ToolbarItemPlacement**：定义工具栏项目位置的结构。
- **ToolbarContent**：符合类型表示可放置在工具栏不同位置的项目。
- **ToolbarContentBuilder**：从多表达式闭包构造工具栏项目集。
- **ToolbarSpacer**：工具栏中的标准空格项。
- **DefaultToolbarItem**：表示系统组件的工具栏项目。

## 填充自定义工具栏

- **toolbar(id:content:)**：用指定的项目填充工具栏或导航栏，允许用户自定义。
- **CustomizableToolbarContent**：符合类型表示可放置在自定义工具栏不同位置的项目。
- **ToolbarCustomizationBehavior**：自定义工具栏内容的自定义行为。
- **ToolbarCustomizationOptions**：影响可定制工具栏内容默认定制行为的选项。
- **SearchToolbarBehavior**：工具栏中搜索字段的行为。

## 删除默认项目

- **toolbar(removing:)**：删除默认存在的工具栏项目
- **ToolbarDefaultItemKind**：`View`默认添加的一种工具栏项。

## 设置工具栏可见性

- **toolbar(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性。
- **toolbarVisibility(_:for:)**：指定由 SwiftUI 管理的条形图的可见性。
- **toolbarBackgroundVisibility(_:for:)**：指定由 SwiftUI 管理的条形图上背景的首选可见性。
- **ToolbarPlacement**：工具栏的位置。
- **ContentToolbarPlacement**：工具栏的位置。

## 指定工具栏内容的角色

- **toolbarRole(_:)**：配置填充工具栏内容的语义角色。
- **ToolbarRole**：填充工具栏内容的目的。

## 工具栏的样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。
- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的条形图的首选配色方案。
- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的条形图的首选前景样式。
- **windowToolbarStyle(_:)**：为在此场景中定义的工具栏设置样式。
- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。
- **toolbarLabelStyle**：应用于工具栏中控件的标签样式。
- **ToolbarLabelStyle**：工具栏的标签样式。
- **SpacerSizing**：工具栏的标签样式：一种定义间隔符大小的类型。

## 配置工具栏标题显示模式

- **toolbarTitleDisplayMode(_:)**：配置此视图的工具栏标题显示模式。
- **ToolbarTitleDisplayMode**：定义工具栏标题行为的类型。

## 设置工具栏标题菜单

- **toolbarTitleMenu(content:)**：配置工具栏的标题菜单。
- **ToolbarTitleMenu**：工具栏的标题菜单。

## 创建装饰物

- **ornament(visibility:attachmentAnchor:contentAlignment:ornament:)**：显示装饰物。
- **OrnamentAttachmentAnchor**：装饰品的连接锚。

## 应用程序结构

- 应用程序组织**：定义应用程序的入口点和顶层结构。
- **Scenes**：声明构成应用程序各部分的用户界面分组。
- **Windows**：在窗口或窗口集合中显示用户界面内容。
- ** 无限空间**：在人的周围显示无限制的内容。
- **Documents**：让人们能够打开和管理文件。
- **Navigation**：使人们能够在场景中的应用程序视图层次结构的不同部分之间移动。
- **模拟演示**：在单独的视图中展示内容，提供集中的交互。
- **Search**：让用户可以在应用程序中搜索文本或其他内容。
- **应用扩展**：将应用程序的基本功能扩展到系统的其他部分，如添加 Widget。


---
source: https://developer.apple.com/documentation/SwiftUI/Toolbars
crawled: 2025-12-02T17:20:46Z
---

# Toolbars

**API Collection**

Provide immediate access to frequently used commands and controls.

## Overview

The system might present toolbars above or below your app’s content, depending on the platform and the context.



Add items to a toolbar by applying the [toolbar(content:)](View/toolbar_content.zh-Hans.md) view modifier to a view in your app. You can also configure the toolbar using view modifiers. For example, you can set the visibility of a toolbar with the [toolbar(_:for:)](View/toolbar___for.zh-Hans.md) modifier.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/toolbars] in the Human Interface Guidelines.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContent**: Conforming types represent items that can be placed in various locations in a toolbar.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

## Populating a customizable toolbar

- **toolbar(id:content:)**: Populates the toolbar or navigation bar with the specified items, allowing for user customization.
- **CustomizableToolbarContent**: Conforming types represent items that can be placed in various locations in a customizable toolbar.
- **ToolbarCustomizationBehavior**: The customization behavior of customizable toolbar content.
- **ToolbarCustomizationOptions**: Options that influence the default customization behavior of customizable toolbar content.
- **SearchToolbarBehavior**: The behavior of a search field in a toolbar.

## Removing default items

- **toolbar(removing:)**: Remove a toolbar item present by default
- **ToolbarDefaultItemKind**: A kind of toolbar item a `View` adds by default.

## Setting toolbar visibility

- **toolbar(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarVisibility(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarBackgroundVisibility(_:for:)**: Specifies the preferred visibility of backgrounds on a bar managed by SwiftUI.
- **ToolbarPlacement**: The placement of a toolbar.
- **ContentToolbarPlacement**

## Specifying the role of toolbar content

- **toolbarRole(_:)**: Configures the semantic role for the content populating the toolbar.
- **ToolbarRole**: The purpose of content that populates the toolbar.

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

## Configuring the toolbar title display mode

- **toolbarTitleDisplayMode(_:)**: Configures the toolbar title display mode for this view.
- **ToolbarTitleDisplayMode**: A type that defines the behavior of title of a toolbar.

## Setting the toolbar title menu

- **toolbarTitleMenu(content:)**: Configure the title menu of a toolbar.
- **ToolbarTitleMenu**: The title menu of a toolbar.

## Creating an ornament

- **ornament(visibility:attachmentAnchor:contentAlignment:ornament:)**: Presents an ornament.
- **OrnamentAttachmentAnchor**: An attachment anchor for an ornament.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

