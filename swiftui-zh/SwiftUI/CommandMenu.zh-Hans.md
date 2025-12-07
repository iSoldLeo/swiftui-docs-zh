---
来源： https://developer.apple.com/documentation/SwiftUI/CommandMenu
抓取时间： 2025-12-02T17:36:21Z
---

# 命令菜单

**Structure**

命令菜单是独立的顶级控件容器，用于执行相关的应用程序特定命令。

### 声明

```swift
struct CommandMenu<Content> where Content : View
```

## 概览

命令菜单在 macOS 上以菜单栏菜单的形式实现，按声明顺序插入内置的 "视图 "和 "窗口 "菜单之间。在 iOS、iPadOS 和 tvOS 上，SwiftUI 会为每个菜单命令创建键盘快捷键。

## 创建命令菜单

- **init(_:content:)**：创建一个带有本地化名称的新菜单，用于收集特定于应用程序的命令，并插入到应用程序菜单的标准位置（位于 "视图 "菜单之后，与其他未明确声明位置的菜单依次排列）。

## 定义命令

- **commands(content:)**：向场景添加命令。
- **commandsRemoved()**：删除修改后的场景定义的所有命令。
- **commandsReplaced(content:)**：用生成器中的命令替换已修改场景定义的所有命令。
- **Commands**：符合类型代表一组相关命令，可通过 macOS 的主菜单和 iOS 的按键命令向用户展示。
- **CommandGroup**：可添加到现有命令菜单的控件组。
- **CommandsBuilder**：从多表达式闭包构建命令集。与`ViewBuilder`一样，它支持在闭包主体中最多包含 10 个表达式。
- **CommandGroupPlacement**：可以相对放置新命令组的标准位置。

## 符合

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/CommandMenu
crawled: 2025-12-02T17:36:21Z
---

# CommandMenu

**Structure**

Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.

## Declaration

```swift
struct CommandMenu<Content> where Content : View
```

## Overview

Command menus are realized as menu bar menus on macOS, inserted between the built-in View and Window menus in order of declaration. On iOS, iPadOS, and tvOS, SwiftUI creates key commands for each of a menu’s commands that has a keyboard shortcut.

## Creating a command menu

- **init(_:content:)**: Creates a new menu with a localized name for a collection of app- specific commands, inserted in the standard location for app menus (after the View menu, in order with other menus declared without an explicit location).

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

## Conforms To

- Commands

