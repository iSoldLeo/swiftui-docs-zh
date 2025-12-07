--- 来源：https://developer.apple.com/documentation/SwiftUI/View/keyboardShortcut(_:modifiers:)

抓取时间：2025-11-30T21:26:43Z

---

# keyboardShortcut(_:modifiers:)

**实例方法**

定义一个键盘快捷键并将其分配给被修改的控件。

## 声明

```swift
nonisolated func keyboardShortcut(_ key: KeyEquivalent, modifiers: EventModifiers = .command) -> some View

```

## 讨论

当控件位于最前面的窗口或场景中，或者位于 macOS 主菜单中的任何位置时，按下该控件的快捷键相当于直接与该控件交互以执行其主要操作。

键盘快捷键的目标位置是通过对一个或多个视图层级进行从前到后的深度优先遍历来确定的。在 macOS 上，系统首先查找按键窗口，然后是主窗口，最后是命令组；在其他平台上，系统会先查找当前活动场景，然后再查找命令组。

如果多个控件关联了同一个快捷键，则使用找到的第一个。

默认本地化配置设置为 [automatic](../KeyboardShortcut/Localization-swift_struct/automatic.zh-Hans.md)。

## 创建键盘快捷键

- **keyboardShortcut(_:)**：为修改后的控件分配键盘快捷键。

- **keyboardShortcut(_:modifiers:localization:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut**：此环境中按钮的触发快捷键。

- **KeyboardShortcut**：键盘快捷键描述了用户可以通过按下键盘上的组合键来激活按钮或切换开关。

- **KeyEquivalent**：按键等效项由字母、标点符号或功能键组成，可与一组可选的修饰键组合，以指定键盘快捷键。

- **EventModifiers**：可添加到手势中的一组修饰键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/keyboardShortcut(_:modifiers:)
crawled: 2025-11-30T21:26:43Z
---

# keyboardShortcut(_:modifiers:)

**Instance Method**

Defines a keyboard shortcut and assigns it to the modified control.

## Declaration

```swift
nonisolated func keyboardShortcut(_ key: KeyEquivalent, modifiers: EventModifiers = .command) -> some View

```

## Discussion

Pressing the control’s shortcut while the control is anywhere in the frontmost window or scene, or anywhere in the macOS main menu, is equivalent to direct interaction with the control to perform its primary action.

The target of a keyboard shortcut is resolved in a leading-to-trailing, depth-first traversal of one or more view hierarchies. On macOS, the system looks in the key window first, then the main window, and then the command groups; on other platforms, the system looks in the active scene, and then the command groups.

If multiple controls are associated with the same shortcut, the first one found is used.

The default localization configuration is set to [automatic](../KeyboardShortcut/Localization-swift_struct/automatic.zh-Hans.md).

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **KeyboardShortcut**: Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.
- **KeyEquivalent**: Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.
- **EventModifiers**: A set of key modifiers that you can add to a gesture.

