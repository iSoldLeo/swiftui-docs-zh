---
来源： https://developer.apple.com/documentation/SwiftUI/Menus-and-commands
抓取时间： 2025-12-02T16:02:51Z
---

# 菜单和命令

** 应用程序集**

根据上下文访问命令和控件，节省空间。

## 概览

使用菜单可让用户轻松访问常用命令。你可以使用[commands(content:)](scene/commands_content.zh-Hans.md)场景修饰符将项目添加到 macOS 或 iPadOS 应用程序的菜单栏中，或使用[contextMenu(menuItems:)](View/contextMenu_menuItems.zh-Hans.md)视图修饰符创建上下文菜单，让用户在当前任务附近显示。



通过嵌套[Menu](Menu.zh-Hans.md) 实例来创建子菜单。使用 [Divider](Divider.zh-Hans.md) 视图在菜单元素之间创建分隔符。

有关设计指导，请参阅《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/menus]。

## 建立菜单栏

- 使用 SwiftUI 构建和自定义菜单栏**：为 iPadOS 和 macOS 构建原生菜单栏，提供无缝、跨平台的用户体验。

## 创建菜单

- 用自适应控件填充 SwiftUI 菜单**：用控件填充菜单，直观地组织内容，从而改进你的应用程序。
- **Menu**：用于显示操作菜单的控件。
- **menuStyle(_:)**：设置该视图中菜单的样式。

## 创建上下文菜单

- **contextMenu(menuItems:)**：为视图添加上下文菜单。
- **contextMenu(menuItems:preview:)**：为视图添加带有自定义预览的上下文菜单。
- **contextMenu(forSelectionType:menu:primaryAction:)**：为视图添加基于项目的上下文菜单。

## 定义命令

- **commands(content:)**：为场景添加命令。
- **commandsRemoved()**：删除修改后的场景定义的所有命令。
- **commandsReplaced(content:)**：用生成器中的命令替换修改后的场景中定义的所有命令。
- **Commands**：符合类型代表一组相关命令，可通过 macOS 的主菜单和 iOS 的按键命令显示给用户。
- **CommandMenu**：命令菜单是独立的顶级控件容器，用于执行相关的应用程序特定命令。
- **CommandGroup**：可添加到现有命令菜单的控件组。
- **CommandsBuilder**：从多表达式闭包构建命令集。与`ViewBuilder`一样，它支持在闭包主体中最多包含 10 个表达式。
- **CommandGroupPlacement**：可以相对放置新命令组的标准位置。

## 获取内置命令组

- **SidebarCommands**：用于操作窗口边栏的内置命令集。
- **TextEditingCommands**：用于搜索、编辑和转换文本选区的内置命令集。
- **TextFormattingCommands**：用于转换应用于文本选区的样式的内置命令集。
- **ToolbarCommands**：用于操作窗口工具栏的内置命令集。
- **ImportFromDevicesCommands**：用于从附近设备导入内容的内置命令集。
- **InspectorCommands**：用于操作检查器的内置命令集。
- **EmptyCommands**：一组空命令。

## 显示菜单指示器

- **menuIndicator(_:)**：设置该视图中控件的菜单指示器可见性。
- **menuIndicatorVisibility**：应用于视图中控件的菜单指示符可见性。

## 配置菜单取消

- **menuActionDismissBehavior(_:)**：告诉菜单在执行操作后是否取消。
- **MenuActionDismissBehavior**：菜单解散行为选项集。

## 设置首选顺序

- **menuOrder(_:)**：设置从该视图显示的菜单的首选项目顺序。
- **menuOrder**：从该视图显示的菜单的首选项目顺序。
- **MenuOrder**：菜单显示内容的顺序。

## 过时类型

- **MenuButton**：按钮，按下时会显示包含一系列选项的菜单。
- **PullDownButton**: 按钮，按下时会显示包含一系列选择的菜单。
- **ContextMenu**：在上下文菜单中作为菜单项显示的视图的容器。

## 视图

- 视图基础**：使用视图层次结构定义应用程序的视觉元素。
- 视图配置**：调整层次结构中视图的特性。
- 视图样式**：为不同类型的视图应用内置和自定义外观和行为。
- **Animations**：根据状态变化创建平滑的可视化更新。
- 文本输入和输出**：显示格式化文本并从用户获取文本输入。
- **Images**：为应用程序的用户界面添加图像和符号。
- **控件和指示器**：显示数值并获取用户选择。
- **Shapes**：用颜色、渐变或其他图案描画和填充内置形状和自定义形状。
- **绘图和图形**：使用图形效果和自定义绘图来增强视图效果。


---
source: https://developer.apple.com/documentation/SwiftUI/Menus-and-commands
crawled: 2025-12-02T16:02:51Z
---

# Menus and commands

**API Collection**

Provide space-efficient, context-dependent access to commands and controls.

## Overview

Use a menu to provide people with easy access to common commands. You can add items to a macOS or iPadOS app’s menu bar using the [commands(content:)](scene/commands_content.zh-Hans.md) scene modifier, or create context menus that people reveal near their current task using the [contextMenu(menuItems:)](View/contextMenu_menuItems.zh-Hans.md) view modifier.



Create submenus by nesting [Menu](Menu.zh-Hans.md) instances inside others. Use a [Divider](Divider.zh-Hans.md) view to create a separator between menu elements.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/menus] in the Human Interface Guidelines.

## Building a menu bar

- **Building and customizing the menu bar with SwiftUI**: Provide a seamless, cross-platform user experience by building a native menu bar for iPadOS and macOS.

## Creating a menu

- **Populating SwiftUI menus with adaptive controls**: Improve your app by populating menus with controls and organizing your content intuitively.
- **Menu**: A control for presenting a menu of actions.
- **menuStyle(_:)**: Sets the style for menus within this view.

## Creating context menus

- **contextMenu(menuItems:)**: Adds a context menu to a view.
- **contextMenu(menuItems:preview:)**: Adds a context menu with a custom preview to a view.
- **contextMenu(forSelectionType:menu:primaryAction:)**: Adds an item-based context menu to a view.

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

## Getting built-in command groups

- **SidebarCommands**: A built-in set of commands for manipulating window sidebars.
- **TextEditingCommands**: A built-in group of commands for searching, editing, and transforming selections of text.
- **TextFormattingCommands**: A built-in set of commands for transforming the styles applied to selections of text.
- **ToolbarCommands**: A built-in set of commands for manipulating window toolbars.
- **ImportFromDevicesCommands**: A built-in set of commands that enables importing content from nearby devices.
- **InspectorCommands**: A built-in set of commands for manipulating inspectors.
- **EmptyCommands**: An empty group of commands.

## Showing a menu indicator

- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **menuIndicatorVisibility**: The menu indicator visibility to apply to controls within a view.

## Configuring menu dismissal

- **menuActionDismissBehavior(_:)**: Tells a menu whether to dismiss after performing an action.
- **MenuActionDismissBehavior**: The set of menu dismissal behavior options.

## Setting a preferred order

- **menuOrder(_:)**: Sets the preferred order of items for menus presented from this view.
- **menuOrder**: The preferred order of items for menus presented from this view.
- **MenuOrder**: The order in which a menu presents its content.

## Deprecated types

- **MenuButton**: A button that displays a menu containing a list of choices when pressed.
- **PullDownButton**
- **ContextMenu**: A container for views that you present as menu items in a context menu.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

