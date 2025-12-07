--- 来源：https://developer.apple.com/documentation/SwiftUI/App-extensions
抓取时间：2025-12-02T17:20:48Z

---

# 应用扩展

**API 集合**

将应用的基本功能扩展到系统的其他部分，例如添加 Widget。

## 概述

使用 SwiftUI 和 [doc://com.apple.documentation/documentation/WidgetKit] 为应用添加 Widget。

Widget 可以快速访问应用中的相关内容。定义一个符合 [Widget](Widget.zh-Hans.md) 协议的结构，并为 Widget 声明一个视图层次结构。像配置其他 SwiftUI 视图一样配置 Widget 内部的视图，使用视图修饰符，包括一些 Widget 特有的修饰符。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/widgets]。

## 创建组件

- **使用 WidgetKit 和 SwiftUI 构建组件**：创建组件，在主屏幕上显示应用内容，并可通过自定义 Intent 实现用户自定义设置。

- **创建组件扩展**：在各种设备上以便捷、信息丰富的组件形式显示应用内容。

- **保持组件更新**：规划组件的时间线，使用动态视图显示及时、相关的信息，并在内容发生变化时更新时间线。

- **创建可配置组件**：允许用户通过向项目中添加自定义应用 Intent 来自定义组件。

- **Widget**：用于在主屏幕或通知中心显示组件的配置和内容。

- **WidgetBundle**：用于从单个组件扩展公开多个组件的容器。

- **LimitedAvailabilityConfiguration**：类型已擦除的控件配置。

- **WidgetConfiguration**：描述控件内容的类型。

- **EmptyWidgetConfiguration**：空的控件配置。

## 组合控件

- **ControlWidget**：要在系统空间（例如控制中心、锁屏界面和操作按钮）中显示的控件的配置和内容。

- **ControlWidgetConfiguration**：描述控件内容的类型。

- **EmptyControlWidgetConfiguration**：空的控件配置。

- **ControlWidgetConfigurationBuilder**：用于构建控件主体的自定义属性。

- **ControlWidgetTemplate**：描述控件内容的类型。

- **EmptyControlWidgetTemplate**：一个空的控件模板。

- **ControlWidgetTemplateBuilder**：一个自定义属性，用于构建控件模板的主体。

- **controlWidgetActionHint(_:)**：修改后的标签所描述的控件的操作提示。

- **controlWidgetStatus(_:)**：修改后的标签所描述的控件的状态。

## 为控件添加标签

- **widgetLabel(_:)**：返回一个本地化的文本标签，用于在辅助控件系列的主 SwiftUI 视图之外显示附加内容。

- **widgetLabel(label:)**：创建一个标签，用于在辅助控件系列的主 SwiftUI 视图之外显示附加内容。

## 设置控件组的样式

- **accessoryWidgetGroupStyle(_:)**：可应用于 `AccessoryWidgetGroup` 的视图修饰符，用于指定三个内容视图的遮罩形状。`style` 的值设置为 `.automatic`，默认值为 `.circular`。

## 控制强调框组

- **widgetAccentable(_:)**：将视图及其所有子视图添加到强调框组中。

## 管理动态岛中的位置

- **dynamicIsland(verticalPlacement:)**：指定动态岛中显示的已展开的 Live Activity 视图的垂直位置。

## 应用结构

- **应用组织结构**：定义应用的入口点和顶级结构。

- **Scenes**：声明构成应用各个部分的用户界面分组。

- **Windows**：在单个窗口或窗口集合中显示用户界面内容。

- **沉浸式空间**：在用户的周围环境中显示无边界的内容。

- **Documents**：允许用户打开和管理文档。

- **Navigation**：允许用户在场景内切换应用视图层级结构的不同部分。

- **模态呈现**：在单独的视图中呈现内容，提供专注的交互体验。

- **Toolbars**：提供对常用命令和控件的快速访问。

- **Search**：允许用户在应用内搜索文本或其他内容。


---
source: https://developer.apple.com/documentation/SwiftUI/App-extensions
crawled: 2025-12-02T17:20:48Z
---

# App extensions

**API Collection**

Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

## Overview

Use SwiftUI along with [doc://com.apple.documentation/documentation/WidgetKit] to add widgets to your app.



Widgets provide quick access to relevant content from your app. Define a structure that conforms to the [Widget](Widget.zh-Hans.md) protocol, and declare a view hierarchy for the widget. Configure the views inside the widget as you do other SwiftUI views, using view modifiers, including a few widget-specific modifiers.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/widgets] in the Human Interface Guidelines.

## Creating widgets

- **Building Widgets Using WidgetKit and SwiftUI**: Create widgets to show your app’s content on the Home screen, with custom intents for user-customizable settings.
- **Creating a widget extension**: Display your app’s content in a convenient, informative widget on various devices.
- **Keeping a widget up to date**: Plan your widget’s timeline to show timely, relevant information using dynamic views, and update the timeline when things change.
- **Making a configurable widget**: Give people the option to customize their widgets by adding a custom app intent to your project.
- **Widget**: The configuration and content of a widget to display on the Home screen or in Notification Center.
- **WidgetBundle**: A container used to expose multiple widgets from a single widget extension.
- **LimitedAvailabilityConfiguration**: A type-erased widget configuration.
- **WidgetConfiguration**: A type that describes a widget’s content.
- **EmptyWidgetConfiguration**: An empty widget configuration.

## Composing control widgets

- **ControlWidget**: The configuration and content of a control widget to display in system spaces such as Control Center, the Lock Screen, and the Action Button.
- **ControlWidgetConfiguration**: A type that describes a control widget’s content.
- **EmptyControlWidgetConfiguration**: An empty control widget configuration.
- **ControlWidgetConfigurationBuilder**: A custom attribute that constructs a control widget’s body.
- **ControlWidgetTemplate**: A type that describes a control widget’s content.
- **EmptyControlWidgetTemplate**: An empty control widget template.
- **ControlWidgetTemplateBuilder**: A custom attribute that constructs a control widget template’s body.
- **controlWidgetActionHint(_:)**: The action hint of the control described by the modified label.
- **controlWidgetStatus(_:)**: The status of the control described by the modified label.

## Labeling a widget

- **widgetLabel(_:)**: Returns a localized text label that displays additional content outside the accessory family widget’s main SwiftUI view.
- **widgetLabel(label:)**: Creates a label for displaying additional content outside an accessory family widget’s main SwiftUI view.

## Styling a widget group

- **accessoryWidgetGroupStyle(_:)**: The view modifier that can be applied to `AccessoryWidgetGroup` to specify the shape the three content views will be masked with. The value of `style` is set to `.automatic`, which is `.circular` by default.

## Controlling the accented group

- **widgetAccentable(_:)**: Adds the view and all of its subviews to the accented group.

## Managing placement in the Dynamic Island

- **dynamicIsland(verticalPlacement:)**: Specifies the vertical placement for a view of an expanded Live Activity that appears in the Dynamic Island.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Scenes**: Declare the user interface groupings that make up the parts of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.

