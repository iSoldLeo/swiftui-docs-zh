--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/keyboardShortcut(_:modifiers:localization:)

抓取时间：2025-12-03T05:31:05Z

---

# keyboardShortcut(_:modifiers:localization:)

**实例方法**

定义用于打开新场景窗口的键盘快捷键。

## 声明

```swift
nonisolated func keyboardShortcut(_ key: KeyEquivalent, modifiers: EventModifiers = .command, localization: KeyboardShortcut.Localization = .automatic) -> some Scene

```

## 参数

- **key**：用户按下以显示场景的等效按键。

- **modifiers**：执行快捷键所需的修饰键。

- **localization**：要应用于快捷键的本地化样式。

## 返回值

一个可以通过键盘快捷键显示的场景。

## 讨论

场景的键盘快捷键绑定到它添加的用于创建新窗口（例如 `WindowGroup` 和 `DocumentGroup`）或将单个窗口置于前台（例如 `Window`，以及 macOS 上的 `Settings`）的命令。按下键盘快捷键相当于选择菜单命令。

如果某个命令已有键盘快捷键，则使用场景的键盘快捷键。例如，`WindowGroup` 通常会创建一个“文件”>“新建窗口”菜单命令，其键盘快捷键为 `⌘N`。以下代码将其更改为 `⌥⌘N`：

```swift
WindowGroup {
    ContentView()
}
.keyboardShortcut("n", modifiers: [.option, .command])
```

### 本地化

提供一个 `localization` 值，以指定此快捷键的本地化方式。

鉴于 `key` 始终与美式英语键盘布局相关，因此在不同的国际键盘布局上可能难以使用。例如，快捷键 `⌘[` 在美国键盘布局下运行良好，但对于德语用户来说却难以使用，因为德语用户需要按下 `⌥5` 才能使用 `[`，这意味着他们需要输入 `⌥⌘5`。自动键盘快捷键重映射功能会将快捷键重新分配给合适的替代快捷键，在本例中为 `⌘Ö`。

提供选项 [custom](../KeyboardShortcut/Localization-swift_struct/custom.zh-Hans.md) 可禁用此快捷键的自动本地化，以告知系统国际化将以其他方式处理。

## 设置命令

- **commands(content:)**：向场景添加命令。

- **commandsRemoved()**：移除已修改场景中定义的所有命令。

- **commandsReplaced(content:)**：将已修改场景中定义的所有命令替换为构建器中的命令。

- **keyboardShortcut(_:)**：定义用于打开新场景窗口的键盘快捷键。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/keyboardShortcut(_:modifiers:localization:)
crawled: 2025-12-03T05:31:05Z
---

# keyboardShortcut(_:modifiers:localization:)

**Instance Method**

Defines a keyboard shortcut for opening new scene windows.

## Declaration

```swift
nonisolated func keyboardShortcut(_ key: KeyEquivalent, modifiers: EventModifiers = .command, localization: KeyboardShortcut.Localization = .automatic) -> some Scene

```

## Parameters

- **key**: The key equivalent the user presses to present the scene.
- **modifiers**: The modifier keys required to perform the shortcut.
- **localization**: The localization style to apply to the shortcut.

## Return Value

A scene that can be presented with a keyboard shortcut.

## Discussion

A scene’s keyboard shortcut is bound to the command it adds for creating new windows (in the case of `WindowGroup` and `DocumentGroup`) or bringing a singleton window forward (in the case of `Window` and, on macOS, `Settings`). Pressing the keyboard shortcut is equivalent to selecting the menu command.

In cases where a command already has a keyboard shortcut, the scene’s keyboard shortcut is used instead. For example, `WindowGroup` normally creates a File > New Window menu command whose keyboard shortcut is `⌘N`. The following code changes it to `⌥⌘N`:

```swift
WindowGroup {
    ContentView()
}
.keyboardShortcut("n", modifiers: [.option, .command])
```

### Localization

Provide a `localization` value to specify how this shortcut should be localized.

Given that `key` is always defined in relation to the US-English keyboard layout, it might be hard to reach on different international layouts. For example the shortcut `⌘[` works well for the US layout but is hard to reach for German users, where `[` is available by pressing `⌥5`, making users type `⌥⌘5`. The automatic keyboard shortcut remapping re-assigns the shortcut to an appropriate replacement, `⌘Ö` in this case.

Providing the option [custom](../KeyboardShortcut/Localization-swift_struct/custom.zh-Hans.md) disables the automatic localization for this shortcut to tell the system that internationalization is taken care of in a different way.

## Setting commands

- **commands(content:)**: Adds commands to the scene.
- **commandsRemoved()**: Removes all commands defined by the modified scene.
- **commandsReplaced(content:)**: Replaces all commands defined by the modified scene with the commands from the builder.
- **keyboardShortcut(_:)**: Defines a keyboard shortcut for opening new scene windows.

