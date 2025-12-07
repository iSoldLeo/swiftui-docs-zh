---
来源： https://developer.apple.com/documentation/SwiftUI/View-Auxiliary-Views
抓取时间： 2025-12-02T17:22:11Z
---

# 辅助视图修改器

**辅助视图修改器

添加和配置辅助视图，如工具栏和上下文菜单。

## 概览

使用这些修改器可管理显示特定上下文控件和信息的补充视图。例如，你可以为导航栏添加标题和按钮，管理状态栏，创建上下文菜单，以及为许多不同类型的视图添加徽章。

## 导航标题

- 配置应用程序的导航标题**：使用导航标题显示界面的当前导航状态。
- **navigationTitle(_:)**：使用字符串绑定配置用于导航的视图标题。
- **navigationSubtitle(_:)**：为导航目的配置视图的副标题。

## 导航标题配置

- **navigationDocument(_:)**：为导航目的配置视图的文档。
- **navigationDocument(_:preview:)**：为导航目的配置视图的文档。

## 导航栏

- **navigationBarBackButtonHidden(_:)**：隐藏视图的导航栏返回按钮。
- **navigationBarTitleDisplayMode(_:)**：配置此视图的标题显示模式。

## 导航堆栈和列

- **navigationDestination(for:destination:)**：将目标视图与呈现的数据类型关联起来，以便在导航堆栈中使用。
- **navigationDestination(isPresented:destination:)**：将目标视图与可用于将视图推送到[NavigationStack](NavigationStack.zh-Hans.md)上的绑定关联。
- **navigationDestination(item:destination:)**：将目标视图与绑定值关联，以便在导航堆栈或导航分割视图中使用
- **navigationSplitViewColumnWidth(_:)**：为包含该视图的列设置固定的首选宽度。
- **navigationSplitViewColumnWidth(min:ideal:max:)**：为包含此视图的列设置灵活的首选宽度。

## 标签视图

- **tabViewCustomization(_:)**：指定应用于选项卡视图侧边栏表示法的自定义设置。
- **defaultAdaptableTabBarPlacement(_:)**：使用自适应侧边栏样式指定选项卡视图中选项卡的默认位置。
- **tabViewSidebarHeader(content:)**：在选项卡视图的侧边栏中添加自定义页眉。
- **tabViewSidebarFooter(content:)**：在选项卡视图的边栏中添加自定义页脚。
- **tabViewSidebarBottomBar(content:)**：在选项卡视图的侧边栏中添加自定义底栏。
- **sectionActions(content:)**：为部分添加自定义操作。

## 工具栏

- **toolbar(content:)**：用指定项目填充工具栏或导航栏。
- **toolbar(id:content:)**：用指定的项目填充工具栏或导航栏，允许用户自定义。
- **toolbar(_:for:)**：指定由 SwiftUI 管理的栏的可见性。
- **toolbar(removing:)**：删除默认存在的工具栏项目
- **toolbarVisibility(_:for:)**：指定由 SwiftUI 管理的工具栏的可见性。
- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的条形图背景的首选形状样式。
- **toolbarBackgroundVisibility(_:for:)**：指定由 SwiftUI 管理的条形图背景的首选可见性。
- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的条形图的首选前景样式。
- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的条形图的首选配色方案。
- **toolbarRole(_:)**：配置填充工具栏内容的语义角色。
- **toolbarTitleMenu(content:)**：配置工具栏的标题菜单。
- **toolbarTitleDisplayMode(_:)**：配置工具栏的标题菜单：配置此视图的工具栏标题显示模式。
- **ornament(visibility:attachmentAnchor:contentAlignment:ornament:)**：显示装饰物。

## 上下文菜单

- **contextMenu(menuItems:)**：为视图添加上下文菜单。
- **contextMenu(menuItems:preview:)**：为视图添加带有自定义预览的上下文菜单。
- **contextMenu(forSelectionType:menu:primaryAction:)**：为视图添加基于项目的上下文菜单。

## 徽章

- **badge(_:)**：根据整数值为视图生成徽章。
- **badgeProminence(_:)**：指定此视图创建的徽章的显著性。

### 帮助文本

- **help(_:)**：使用您提供的文本视图为视图添加帮助文本。

## 状态栏

- **statusBarHidden(_:)**：设置状态栏的可见性。

## 触摸栏

- **touchBar(content:)**：设置触摸栏显示的内容。
- **touchBar(_:)**：设置 Touch Bar 中要显示的内容。
- **touchBarItemPrincipal(_:)**：设置对该触摸栏有特殊意义的主要视图。
- **touchBarCustomizationLabel(_:)**：设置用户可见的字符串，用于标识视图的功能。
- **touchBarItemPresence(_:)**：设置用户自定义视图的行为。

## 配置视图元素

- **可访问性修改器**：让每个人（包括残障人士）都能访问您的 SwiftUI 应用程序。
- 外观修改器***：配置视图的前景和背景样式、控件和可见性。
- 文本和符号修改器**：管理视图中文本的渲染、选择和输入。
- 图表视图修改器**：配置使用 Swift 图表声明的图表。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Auxiliary-Views
crawled: 2025-12-02T17:22:11Z
---

# Auxiliary view modifiers

**API Collection**

Add and configure supporting views, like toolbars and context menus.

## Overview

Use these modifiers to manage supplemental views that present context-specific controls and information. For example, you can add titles and buttons to navigation bars, manage the status bar, create context menus, and add badges many different kinds of views.

## Navigation titles

- **Configure your apps navigation titles**: Use a navigation title to display the current navigation state of an interface.
- **navigationTitle(_:)**: Configures the view’s title for purposes of navigation, using a string binding.
- **navigationSubtitle(_:)**: Configures the view’s subtitle for purposes of navigation.

## Navigation title configuration

- **navigationDocument(_:)**: Configures the view’s document for purposes of navigation.
- **navigationDocument(_:preview:)**: Configures the view’s document for purposes of navigation.

## Navigation bars

- **navigationBarBackButtonHidden(_:)**: Hides the navigation bar back button for the view.
- **navigationBarTitleDisplayMode(_:)**: Configures the title display mode for this view.

## Navigation stacks and columns

- **navigationDestination(for:destination:)**: Associates a destination view with a presented data type for use within a navigation stack.
- **navigationDestination(isPresented:destination:)**: Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](NavigationStack.zh-Hans.md).
- **navigationDestination(item:destination:)**: Associates a destination view with a bound value for use within a navigation stack or navigation split view
- **navigationSplitViewColumnWidth(_:)**: Sets a fixed, preferred width for the column containing this view.
- **navigationSplitViewColumnWidth(min:ideal:max:)**: Sets a flexible, preferred width for the column containing this view.

## Tab views

- **tabViewCustomization(_:)**: Specifies the customizations to apply to the sidebar representation of the tab view.
- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **sectionActions(content:)**: Adds custom actions to a section.

## Toolbars

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **toolbar(id:content:)**: Populates the toolbar or navigation bar with the specified items, allowing for user customization.
- **toolbar(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbar(removing:)**: Remove a toolbar item present by default
- **toolbarVisibility(_:for:)**: Specifies the visibility of a bar managed by SwiftUI.
- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarBackgroundVisibility(_:for:)**: Specifies the preferred visibility of backgrounds on a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarRole(_:)**: Configures the semantic role for the content populating the toolbar.
- **toolbarTitleMenu(content:)**: Configure the title menu of a toolbar.
- **toolbarTitleDisplayMode(_:)**: Configures the toolbar title display mode for this view.
- **ornament(visibility:attachmentAnchor:contentAlignment:ornament:)**: Presents an ornament.

## Context menus

- **contextMenu(menuItems:)**: Adds a context menu to a view.
- **contextMenu(menuItems:preview:)**: Adds a context menu with a custom preview to a view.
- **contextMenu(forSelectionType:menu:primaryAction:)**: Adds an item-based context menu to a view.

## Badges

- **badge(_:)**: Generates a badge for the view from an integer value.
- **badgeProminence(_:)**: Specifies the prominence of badges created by this view.

## Help text

- **help(_:)**: Adds help text to a view using a text view that you provide.

## Status bar

- **statusBarHidden(_:)**: Sets the visibility of the status bar.

## Touch Bar

- **touchBar(content:)**: Sets the content that the Touch Bar displays.
- **touchBar(_:)**: Sets the Touch Bar content to be shown in the Touch Bar when applicable.
- **touchBarItemPrincipal(_:)**: Sets principal views that have special significance to this Touch Bar.
- **touchBarCustomizationLabel(_:)**: Sets a user-visible string that identifies the view’s functionality.
- **touchBarItemPresence(_:)**: Sets the behavior of the user-customized view.

## Configuring view elements

- **Accessibility modifiers**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Appearance modifiers**: Configure a view’s foreground and background styles, controls, and visibility.
- **Text and symbol modifiers**: Manage the rendering, selection, and entry of text in your view.
- **Chart view modifiers**: Configure charts that you declare with Swift Charts.

