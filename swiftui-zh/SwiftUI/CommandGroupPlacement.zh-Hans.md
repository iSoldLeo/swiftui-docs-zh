--- 来源：https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement
抓取时间：2025-12-02T17:36:23Z

---

# 命令组放置

**Structure**

您可以相对于这些标准位置放置新的命令组。

## 声明

```swift
struct CommandGroupPlacement
```

## 概述

这些放置位置的名称不会显示在用户界面中，但每个放置位置的说明中列出了它包含的项目。

## 应用交互

- **appInfo**：用于放置提供应用信息、用户许可协议条款等的命令。

- **appSettings**：用于放置显示应用设置和偏好的命令。

- **appTermination**：用于执行导致应用程序终止的命令。

- **appVisibility**：用于执行控制正在运行的应用程序可见性的命令。

- **systemServices**：用于执行公开其他应用程序提供的服务的命令。

## 文件操作

- **importExport**：用于执行与导入和导出应用程序本身不支持的格式相关的数据的命令。

- **newItem**：用于执行创建不同类型文档的命令。

- **printItem**：用于执行与打印应用程序内容相关的命令。

- **saveItem**：用于执行保存打开的文档和关闭窗口的命令。

## 内容更新

- **pasteboard**：用于与剪贴板交互并操作应用程序视图层级结构中当前选定内容的命令。

- **textEditing**：用于操作和转换文本选定内容的命令。

- **textFormatting**：用于操作和转换应用于文本选定内容的样式的命令。

- **undoRedo**：用于控制撤销管理器的命令。

## 工具栏

- **sidebar**：用于控制应用程序侧边栏和全屏模式的命令。

- **toolbar**：用于操作工具栏的命令。

## 窗口

- **singleWindowList**：用于描述和显示应用程序定义的任何窗口的命令。

- **windowArrangement**：用于排列应用程序所有窗口的命令位置。

- **windowList**：用于描述和显示应用程序已打开窗口的命令位置。

- **windowSize**：用于控制窗口大小的命令位置。

## 帮助

- **help**：用于向用户显示文档和实用信息的命令位置。

## 定义命令

- **commands(content:)**：向场景添加命令。

- **commandsRemoved()**：移除已修改场景中定义的所有命令。

- **commandsReplaced(content:)**：将已修改场景中定义的所有命令替换为构建器中的命令。

- **Commands**：符合规范的类型表示一组相关的命令，这些命令可以通过 macOS 的主菜单和 iOS 的快捷键向用户公开。

- **CommandMenu**：命令菜单是独立的顶级容器，用于存放执行相关应用程序特定命令的控件。

- **CommandGroup**：可以添加到现有命令菜单中的控件组。

- **CommandsBuilder**：从多表达式闭包构造命令集。与 `ViewBuilder` 类似，它在闭包主体中最多支持十个表达式。

## 符合以下规范

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement
crawled: 2025-12-02T17:36:23Z
---

# CommandGroupPlacement

**Structure**

The standard locations that you can place new command groups relative to.

## Declaration

```swift
struct CommandGroupPlacement
```

## Overview

The names of these placements aren’t visible in the user interface, but the discussion for each placement lists the items that it includes.

## App interactions

- **appInfo**: Placement for commands that provide information about the app, the terms of the user’s license agreement, and so on.
- **appSettings**: Placement for commands that expose app settings and preferences.
- **appTermination**: Placement for commands that result in app termination.
- **appVisibility**: Placement for commands that control the visibility of running apps.
- **systemServices**: Placement for commands that expose services other apps provide.

## File manipulation

- **importExport**: Placement for commands that relate to importing and exporting data using formats that the app doesn’t natively support.
- **newItem**: Placement for commands that create different kinds of documents.
- **printItem**: Placement for commands related to printing app content.
- **saveItem**: Placement for commands that save open documents and close windows.

## Content updates

- **pasteboard**: Placement for commands that interact with the Clipboard and manipulate content that is currently selected in the app’s view hierarchy.
- **textEditing**: Placement for commands that manipulate and transform text selections.
- **textFormatting**: Placement for commands that manipulate and transform the styles applied to text selections.
- **undoRedo**: Placement for commands that control the Undo Manager.

## Bars

- **sidebar**: Placement for commands that control the app’s sidebar and full-screen modes.
- **toolbar**: Placement for commands that manipulate the toolbar.

## Windows

- **singleWindowList**: Placement for commands that describe and reveal any windows that the app defines.
- **windowArrangement**: Placement for commands that arrange all of an app’s windows.
- **windowList**: Placement for commands that describe and reveal the app’s open windows.
- **windowSize**: Placement for commands that control the size of the window.

## Help

- **help**: Placement for commands that present documentation and helpful information to people.

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.

## Conforms To

- Sendable
- SendableMetatype

