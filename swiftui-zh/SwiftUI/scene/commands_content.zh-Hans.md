---

来源：https://developer.apple.com/documentation/SwiftUI/Scene/commands(content:)

抓取时间：2025-11-30T21:21:24Z

---

# commands(content:)

**实例方法**

向场景添加命令。

## 声明

```swift
nonisolated func commands<Content>(@CommandsBuilder content: () -> Content) -> some Scene where Content : Commands

```

## 讨论

命令在不同的平台上以不同的方式实现。在 macOS 上，主菜单使用可用的命令菜单和命令组来组织其主菜单项。每个菜单都以顶级菜单栏菜单的形式呈现，每个命令组在其中一个顶级菜单中都有一组对应的菜单项，菜单项之间由分隔符分隔。

在 iPadOS 上，带有键盘快捷键的命令会显示在快捷键发现 HUD 中，用户按住 Command (⌘) 键即可看到该 HUD。

## 定义命令

- **commandsRemoved()**：移除所有由修改后的场景定义的命令。

- **commandsReplaced(content:)**：将所有由修改后的场景定义的命令替换为构建器中的命令。

- **Commands**：符合规范的类型表示一组相关的命令，这些命令可以通过 macOS 上的主菜单和 iOS 上的快捷键向用户公开。

- **CommandMenu**：命令菜单是独立的顶级容器，用于存放执行相关应用程序特定命令的控件。

- **CommandGroup**：可以添加到现有命令菜单的控件组。

- **CommandsBuilder**：从多表达式闭包构造命令集。与 `ViewBuilder` 类似，它在闭包主体中最多支持十个表达式。

- **CommandGroupPlacement**：您可以相对于这些标准位置放置新的命令组。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/commands(content:)
crawled: 2025-11-30T21:21:24Z
---

# commands(content:)

**Instance Method**

Adds commands to the scene.

## Declaration

```swift
nonisolated func commands<Content>(@CommandsBuilder content: () -> Content) -> some Scene where Content : Commands

```

## Discussion

Commands are realized in different ways on different platforms. On macOS, the main menu uses the available command menus and groups to organize its main menu items. Each menu is represented as a top-level menu bar menu, and each command group has a corresponding set of menu items in one of the top-level menus, delimited by separator menu items.

On iPadOS, commands with keyboard shortcuts are exposed in the shortcut discoverability HUD that users see when they hold down the Command (⌘) key.

## Defining commands

- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

