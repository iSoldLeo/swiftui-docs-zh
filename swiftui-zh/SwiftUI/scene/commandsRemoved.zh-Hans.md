--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/commandsRemoved()

抓取时间：2025-12-02T17:36:17Z

---

# commandsRemoved()

**实例方法**

移除已修改场景中定义的所有命令。

## 声明

```swift
nonisolated func commandsRemoved() -> some Scene

```

## 返回值

一个已移除其子场景中所有命令的场景。

## 说明

`WindowGroup`、`Window` 和其他场景类型都默认包含一组关联的命令。将此修饰符应用于场景即可排除这些命令。

例如，以下代码添加了一个场景，用于在单独的窗口中显示单个数据模型的详细信息。为确保窗口只能通过编程方式显示，我们将移除场景中的命令，包括“文件”>“新建笔记窗口”。

```swift
@main
struct Example: App {
    var body: some Scene {
        ...

        WindowGroup("Note", id: "note", for: Note.ID.self) {
            NoteDetailView(id: $0)
        }
        .commandsRemoved()
    }
}
```

## 定义命令

- **commands(content:)**：向场景添加命令。

- **commandsReplaced(content:)**：将修改后的场景中定义的所有命令替换为构建器中的命令。

- **Commands**：符合规范的类型表示一组相关的命令，这些命令可以通过 macOS 上的主菜单和 iOS 上的快捷键向用户显示。

- **CommandMenu**：命令菜单是独立的顶级容器，用于存放执行相关应用程序特定命令的控件。

- **CommandGroup**：您可以添加到现有命令菜单中的控件组。

- **CommandsBuilder**：从多表达式闭包构建命令集。与 `ViewBuilder` 类似，它支持闭包主体中最多包含十个表达式。

- **CommandGroupPlacement**：您可以相对于这些标准位置放置新的命令组。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/commandsRemoved()
crawled: 2025-12-02T17:36:17Z
---

# commandsRemoved()

**Instance Method**

Removes all commands defined by the modified scene.

## Declaration

```swift
nonisolated func commandsRemoved() -> some Scene

```

## Return Value

A scene that excludes any commands defined by its children.

## Discussion

`WindowGroup`, `Window`, and other scene types all have an associated set of commands that they include by default. Apply this modifier to a scene to exclude those commands.

For example, the following code adds a scene for presenting the details of an individual data model in a separate window. To ensure that the window can only appear programmatically, we remove the scene’s commands, including File > New Note Window.

```swift
@main
struct Example: App {
    var body: some Scene {
        ...

        WindowGroup("Note", id: "note", for: Note.ID.self) {
            NoteDetailView(id: $0)
        }
        .commandsRemoved()
    }
}
```

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

