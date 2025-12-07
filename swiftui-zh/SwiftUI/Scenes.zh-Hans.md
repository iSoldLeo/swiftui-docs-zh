---
来源： https://developer.apple.com/documentation/SwiftUI/Scenes
抓取时间： 2025-12-02T17:20:42Z
---

# 场景

** 应用程序集**

声明构成应用程序各部分的用户界面分组。

## 概览

场景代表应用程序用户界面的一部分，其生命周期由系统管理。一个[App](App.zh-Hans.md)实例展示了它所包含的场景，而每个[Scene](Scene.zh-Hans.md)则充当[View](View.zh-Hans.md)层次结构的根元素。



系统会根据场景的类型、平台和上下文以不同的方式呈现场景。场景可能占满整个显示屏、显示屏的一部分、一个窗口、窗口中的一个标签页或其他内容。在某些情况下，您的应用程序还可以同时显示多个场景实例，例如当用户根据您应用程序中的单个[WindowGroup](WindowGroup.zh-Hans.md) 声明同时打开多个窗口时。有关主要内置场景类型的更多信息，请参阅 [Windows](Windows.zh-Hans.md) 和 [Documents](Documents.zh-Hans.md)。

使用修改器配置场景的方法与配置视图的方法类似。例如，您可以使用[windowStyle(_:)](scene/windowStyle.zh-Hans.md) 修饰符调整包含场景的窗口的外观（如果场景恰好出现在窗口中）。同样，您也可以使用[commands(content:)](scene/commands_content.zh-Hans.md)修改器添加菜单命令，当场景在某些平台上处于前景时，这些命令就会可用。

## 创建场景

- **Scene**：应用程序用户界面的一部分，其生命周期由系统管理。
- **SceneBuilder**：用于将场景集合合成为单一复合场景的结果生成器。

## 监控场景生命周期

- **scenePhase**：场景的当前阶段。
- **ScenePhase**：场景运行状态的指示。

## 管理设置窗口

- **Settings**：显示用于查看和修改应用程序设置的界面的场景。
- **SettingsLink**：打开应用程序定义的 "设置 "场景的视图。
- **OpenSettingsAction**：显示应用程序设置场景的操作。
- **openSettings**：存储在视图环境中的设置演示操作。

## 构建菜单栏

- 使用 SwiftUI 构建和自定义菜单栏**：为 iPadOS 和 macOS 构建原生菜单栏，提供无缝的跨平台用户体验。

## 额外创建菜单栏

- **MenuBarExtra**：将自己渲染为系统菜单栏中一个持久控件的场景。
- **menuBarExtraStyle(_:)**：设置此场景创建的菜单栏额外控件的样式。
- **MenuBarExtraStyle**：菜单栏额外场景的外观和行为规范。

## 创建观察通知

- **WKNotificationScene**：收到指定类别的远程或本地通知时出现的场景。

## 应用程序结构

- 应用程序组织**：定义应用程序的入口点和顶层结构。
- **Windows**：在窗口或窗口集合中显示用户界面内容。
- ** 无限空间**：在人的周围显示无限制的内容。
- **Documents**：让人们能够打开和管理文件。
- **Navigation**：使人们能够在场景中的应用程序视图层次结构的不同部分之间移动。
- **模拟演示**：在单独的视图中展示内容，提供集中的交互。
- **Toolbars**：提供对常用命令和控件的即时访问。
- **Search**：使人们能够在您的应用程序中搜索文本或其他内容。
- **应用扩展**：将应用程序的基本功能扩展到系统的其他部分，如添加 Widget。


---
source: https://developer.apple.com/documentation/SwiftUI/Scenes
crawled: 2025-12-02T17:20:42Z
---

# Scenes

**API Collection**

Declare the user interface groupings that make up the parts of your app.

## Overview

A scene represents a part of your app’s user interface that has a life cycle that the system manages. An [App](App.zh-Hans.md) instance presents the scenes it contains, while each [Scene](Scene.zh-Hans.md) acts as the root element of a [View](View.zh-Hans.md) hierarchy.



The system presents scenes in different ways depending on the type of scene, the platform, and the context. A scene might fill the entire display, part of the display, a window, a tab in a window, or something else. In some cases, your app might also be able to display more than one instance of the scene at a time, like when a user simultaneously opens multiple windows based on a single [WindowGroup](WindowGroup.zh-Hans.md) declaration in your app. For more information about the primary built-in scene types, see [Windows](Windows.zh-Hans.md) and [Documents](Documents.zh-Hans.md).

You configure scenes using modifiers, similar to how you configure views. For example, you can adjust the appearance of the window that contains a scene — if the scene happens to appear in a window — using the [windowStyle(_:)](scene/windowStyle.zh-Hans.md) modifier. Similarly, you can add menu commands that become available when the scene is in the foreground on certain platforms using the [commands(content:)](scene/commands_content.zh-Hans.md) modifier.

## Creating scenes

- **Scene**: A part of an app’s user interface with a life cycle managed by the system.
- **SceneBuilder**: A result builder for composing a collection of scenes into a single composite scene.

## Monitoring scene life cycle

- **scenePhase**: The current phase of the scene.
- **ScenePhase**: An indication of a scene’s operational state.

## Managing a settings window

- **Settings**: A scene that presents an interface for viewing and modifying an app’s settings.
- **SettingsLink**: A view that opens the Settings scene defined by an app.
- **OpenSettingsAction**: An action that presents the settings scene for an app.
- **openSettings**: A Settings presentation action stored in a view’s environment.

## Building a menu bar

- **Building and customizing the menu bar with SwiftUI**: Provide a seamless, cross-platform user experience by building a native menu bar for iPadOS and macOS.

## Creating a menu bar extra

- **MenuBarExtra**: A scene that renders itself as a persistent control in the system menu bar.
- **menuBarExtraStyle(_:)**: Sets the style for menu bar extra created by this scene.
- **MenuBarExtraStyle**: A specification for the appearance and behavior of a menu bar extra scene.

## Creating watch notifications

- **WKNotificationScene**: A scene which appears in response to receiving the specified category of remote or local notifications.

## App structure

- **App organization**: Define the entry point and top-level structure of your app.
- **Windows**: Display user interface content in a window or a collection of windows.
- **Immersive spaces**: Display unbounded content in a person’s surroundings.
- **Documents**: Enable people to open and manage documents.
- **Navigation**: Enable people to move between different parts of your app’s view hierarchy within a scene.
- **Modal presentations**: Present content in a separate view that offers focused interaction.
- **Toolbars**: Provide immediate access to frequently used commands and controls.
- **Search**: Enable people to search for text or other content within your app.
- **App extensions**: Extend your app’s basic functionality to other parts of the system, like by adding a Widget.

