--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/keyboardShortcut(_:)

抓取时间：2025-12-01T10:20:10Z

---

# keyboardShortcut(_:)

**实例方法**

定义用于打开新场景窗口的键盘快捷键。

## 声明

```swift
nonisolated func keyboardShortcut(_ shortcut: KeyboardShortcut?) -> some Scene

```

## 参数

- **shortcut**：用于显示场景的键盘快捷键，或 `nil`。

## 返回值

一个可以使用键盘快捷键显示的场景。

## 讨论

场景的键盘快捷键绑定到它添加的用于创建新窗口（例如 `WindowGroup` 和 `DocumentGroup`）或将单个窗口置于前台（例如 `Window`，以及 macOS 上的 `Settings` 和 `UtilityWindow`）的命令。按下键盘快捷键相当于选择菜单命令。

如果某个命令已有键盘快捷键，则使用场景的键盘快捷键。例如，`WindowGroup` 通常会创建一个“文件”>“新建窗口”菜单命令，其键盘快捷键为 `⌘N`。以下代码会根据动态状态将其更改为其他值：

```swift
@main
struct Notes: App {
    @State private var newWindowShortcut: KeyboardShortcut? = ...

    var body: some Scene {
        WindowGroup {
            ContentView($newWindowShortcut)
        }
        .keyboardShortcut(newWindowShortcut)
    }
}
```

如果 `shortcut` 为 `nil`，则场景的显示命令将不会关联键盘快捷键，即使 SwiftUI 通常会自动分配一个快捷键。

## 设置命令

- **commands(content:)**：向场景添加命令。

- **commandsRemoved()**：移除已修改场景中定义的所有命令。

- **commandsReplaced(content:)**：将已修改场景中定义的所有命令替换为构建器中的命令。

- **keyboardShortcut(_:modifiers:localization:)**：定义用于打开新场景窗口的键盘快捷键。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/keyboardShortcut(_:)
crawled: 2025-12-01T10:20:10Z
---

# keyboardShortcut(_:)

**Instance Method**

Defines a keyboard shortcut for opening new scene windows.

## Declaration

```swift
nonisolated func keyboardShortcut(_ shortcut: KeyboardShortcut?) -> some Scene

```

## Parameters

- **shortcut**: The keyboard shortcut for presenting the scene, or `nil`.

## Return Value

A scene that can be presented with a keyboard shortcut.

## Discussion

A scene’s keyboard shortcut is bound to the command it adds for creating new windows (in the case of `WindowGroup` and `DocumentGroup`) or bringing a singleton window forward (in the case of `Window` and, on macOS, `Settings` and `UtilityWindow`). Pressing the keyboard shortcut is equivalent to selecting the menu command.

In cases where a command already has a keyboard shortcut, the scene’s keyboard shortcut is used instead. For example, `WindowGroup` normally creates a File > New Window menu command whose keyboard shortcut is `⌘N`. The following code changes it to something based on dynamic state:

```swift
@main
struct Notes: App {
    @State private var newWindowShortcut: KeyboardShortcut? = ...

    var body: some Scene {
        WindowGroup {
            ContentView($newWindowShortcut)
        }
        .keyboardShortcut(newWindowShortcut)
    }
}
```

If `shortcut` is `nil`, the scene’s presentation command will not be associated with a keyboard shortcut, even if SwiftUI normally assigns one automatically.

## Setting commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut for opening new scene windows.

