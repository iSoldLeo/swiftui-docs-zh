---
来源：https://developer.apple.com/documentation/SwiftUI/CommandGroup
抓取时间： 2025-12-02T17:36:21Z
---

# 命令组

**Structure**

可以添加到现有命令菜单的控件组。

## 声明

```swift
struct CommandGroup<Content> where Content : View
```

## 概览

在 macOS 中，SwiftUI 将命令组作为菜单栏菜单中的菜单项集合来实现。在 iOS、iPadOS 和 tvOS 中，SwiftUI 会为每个命令组创建键盘快捷键。

## 创建命令组

- **init(after:addition:)**：描述将给定视图添加到指定命令组末尾的值。
- **init(before:addition:)**：描述将给定视图添加到指定组开始处的值。
- **init(replacing:addition:)**：描述用给定视图完全替换指定组内容的值。

## 定义命令

- **commands(content:)**：向场景添加命令。
- **commandsRemoved()**：删除修改后的场景定义的所有命令。
- **commandsReplaced(content:)**：用生成器中的命令替换已修改场景定义的所有命令。
- **Commands**：符合类型代表一组相关命令，可通过 macOS 的主菜单和 iOS 的按键命令向用户展示。
- **CommandMenu**：命令菜单是独立的顶级控件容器，用于执行相关的应用程序特定命令。
- **CommandsBuilder**：通过多表达式闭包构造命令集。与`ViewBuilder`一样，它在闭包主体中最多支持 10 个表达式。
- **CommandGroupPlacement**：可以相对放置新命令组的标准位置。

## 符合

- 命令


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroup
crawled: 2025-12-02T17:36:21Z
---

# CommandGroup

**Structure**

Groups of controls that you can add to existing command menus.

## Declaration

```swift
struct CommandGroup<Content> where Content : View
```

## Overview

In macOS, SwiftUI realizes command groups as collections of menu items in a menu bar menu. In iOS, iPadOS, and tvOS, SwiftUI creates key commands for each of a group’s commands that has a keyboard shortcut.

## Creating a command group

- **init(after:addition:)**: A value describing the addition of the given views to the end of the indicated group.
- **init(before:addition:)**: A value describing the addition of the given views to the beginning of the indicated group.
- **init(replacing:addition:)**: A value describing the complete replacement of the contents of the indicated group with the given views.

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

## Conforms To

- Commands

