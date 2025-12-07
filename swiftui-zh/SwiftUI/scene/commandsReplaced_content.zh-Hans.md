--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/commandsReplaced(content:)

抓取时间：2025-12-02T17:36:18Z

---

# commandsReplaced(content:)

**实例方法**

将修改后的场景中定义的所有命令替换为构建器中的命令。

## 声明

```swift
nonisolated func commandsReplaced<Content>(@CommandsBuilder content: () -> Content) -> some Scene where Content : Commands

```

## 参数

- **content**：一个构建器，其输出将用于替换修改后的场景通常提供的命令。

## 返回值

一个场景，该场景将其子场景中定义的任何命令替换为替代内容。

## 讨论

`WindowGroup`、`Window` 和其他场景类型都默认包含一组关联的命令。将此修改器应用于场景，即可将这些命令替换为给定构建器的输出。

例如，以下代码添加了一个场景，用于在专用窗口中显示剪贴板的内容。我们将场景的默认“窗口”>“剪贴板”菜单命令替换为自定义的“编辑”>“显示剪贴板”命令，并将其放置在其他剪贴板命令旁边。

```swift
@main
struct Example: App {
    @Environment(\.openWindow) var openWindow

    var body: some Scene {
        ...

        Window("Clipboard", id: "clipboard") {
            ClipboardContentView()
        }
        .commandsReplaced {
            CommandGroup(after: .pasteboard) {
                Section {
                    Button("Show Clipboard") {
                        openWindow(id: "clipboard")
                    }
                }
            }
        }
    }
}
```

## 定义命令

- **commands(content:)**：向场景添加命令。

- **commandsRemoved()**：移除已修改场景中定义的所有命令。

- **Commands**：符合规范的类型表示一组相关的命令，这些命令可以通过 macOS 的主菜单和 iOS 的快捷键向用户公开。

- **CommandMenu**：命令菜单是独立的顶级容器，用于存放执行相关应用程序特定命令的控件。

- **CommandGroup**：可以添加到现有命令菜单的控件组。

- **CommandsBuilder**：从多表达式闭包构造命令集。与 `ViewBuilder` 类似，它在闭包主体中最多支持十个表达式。

- **CommandGroupPlacement**：可以放置新命令组的标准位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/commandsReplaced(content:)
crawled: 2025-12-02T17:36:18Z
---

# commandsReplaced(content:)

**Instance Method**

Replaces all commands defined by the modified scene with the commands from the builder.

## Declaration

```swift
nonisolated func commandsReplaced<Content>(@CommandsBuilder content: () -> Content) -> some Scene where Content : Commands

```

## Parameters

- **content**: A `Commands` builder whose output will be used to replace the commands normally provided by the modified scene.

## Return Value

A scene that replaces any commands defined by its children with alternative content.

## Discussion

`WindowGroup`, `Window`, and other scene types all have an associated set of commands that they include by default. Apply this modifier to a scene to replace those commands with the output from the given builder.

For example, the following code adds a scene for showing the contents of the pasteboard in a dedicated window. We replace the scene’s default Window > Clipboard menu command with a custom Edit > Show Clipboard command that we place next to the other pasteboard commands.

```swift
@main
struct Example: App {
    @Environment(\.openWindow) var openWindow

    var body: some Scene {
        ...

        Window("Clipboard", id: "clipboard") {
            ClipboardContentView()
        }
        .commandsReplaced {
            CommandGroup(after: .pasteboard) {
                Section {
                    Button("Show Clipboard") {
                        openWindow(id: "clipboard")
                    }
                }
            }
        }
    }
}
```

## Defining commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **Commands**: Conforming types represent a group of related commands that can be exposed to the user via the main menu on macOS and key commands on iOS.
- **CommandMenu**: Command menus are stand-alone, top-level containers for controls that perform related, app-specific commands.
- **CommandGroup**: Groups of controls that you can add to existing command menus.
- **CommandsBuilder**: Constructs command sets from multi-expression closures. Like `ViewBuilder`, it supports up to ten expressions in the closure body.
- **CommandGroupPlacement**: The standard locations that you can place new command groups relative to.

