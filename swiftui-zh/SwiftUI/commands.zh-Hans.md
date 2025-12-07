--- 来源：https://developer.apple.com/documentation/swiftui/commands

抓取时间：2025-12-04T13:23:26Z

---

# 命令

**Protocol**

符合此协议的类型代表一组相关的命令，这些命令可以通过 macOS 的主菜单和 iOS 的快捷键向用户公开。

## 声明

```swift
@MainActor @preconcurrency protocol Commands
```

## 概述

如果类型的基本声明中包含符合此协议的声明，则符合此协议的类型将继承来自该协议的隔离性：`@preconcurrency @MainActor`

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下，隔离到主要参与者，但这不是必需的。在扩展中声明一致性，以选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 实现命令

- **body**：命令层次结构的内容。

- **Body**：代表此命令层次结构主体的命令类型。

## 定义命令

- **commands(content:)**：向场景添加命令。

- **commandsRemoved()**：移除已修改场景中定义的所有命令。

- **commandsReplaced(content:)**：将已修改场景中定义的所有命令替换为构建器中的命令。

- **CommandMenu**：命令菜单是独立的顶级容器，用于存放执行相关应用程序特定命令的控件。

- **CommandGroup**：可添加到现有命令菜单的控件组。

- **CommandsBuilder**：从多表达式闭包构建命令集。与 `ViewBuilder` 类似，它支持闭包主体中最多包含十个表达式。

- **CommandGroupPlacement**：可放置新命令组的标准位置。

## 符合规范的类型

- CommandGroup

- CommandMenu

- EmptyCommands

- Group

- ImportFromDevicesCommands

- InspectorCommands

- SidebarCommands

- TextEditingCommands

- TextFormattingCommands

- ToolbarCommands


---
source: https://developer.apple.com/documentation/swiftui/commands
crawled: 2025-12-04T13:23:26Z
---

# Commands

**Protocol**

Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.

## Declaration

```swift
@MainActor @preconcurrency protocol Commands
```

## Overview

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Implementing commands

- **body**: The contents of the command hierarchy.
- **Body**: The type of commands that represents the body of this command hierarchy.

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

## Conforming Types

- CommandGroup
- CommandMenu
- EmptyCommands
- Group
- ImportFromDevicesCommands
- InspectorCommands
- SidebarCommands
- TextEditingCommands
- TextFormattingCommands
- ToolbarCommands

