--- 来源：https://developer.apple.com/documentation/SwiftUI/View/keyboardShortcut(_:modifiers:localization:)

抓取时间：2025-12-02T17:41:41Z

---

# keyboardShortcut(_:modifiers:localization:)

**实例方法**

定义一个键盘快捷键并将其分配给被修改的控件。

## 声明

```swift
nonisolated func keyboardShortcut(_ key: KeyEquivalent, modifiers: EventModifiers = .command, localization: KeyboardShortcut.Localization) -> some View

```

## 讨论

当控件位于最前面的窗口或场景中，或者位于 macOS 主菜单中的任何位置时，按下该控件的快捷键相当于直接与该控件交互以执行其主要操作。

键盘快捷键的目标位置是通过对一个或多个视图层级进行从前到后的深度优先遍历来确定的。在 macOS 上，系统首先查找按键窗口，然后是主窗口，最后是命令组；在其他平台上，系统会先查找当前活动场景，然后再查找命令组。

如果多个控件与同一个快捷键关联，则使用找到的第一个控件。

### 本地化

提供一个 `localization` 值来指定此快捷键的本地化方式。由于 `key` 始终与美式英语键盘布局相关联，因此在不同的国际键盘布局上可能难以按到。例如，快捷键 `⌘[` 在美国键盘布局下运行良好，但对于德语用户来说却难以按到，因为德语用户需要按下 `⌥5` 才能使用 `[`，这意味着他们需要输入 `⌥⌘5`。自动键盘快捷键重映射会将快捷键重新分配给合适的替代快捷键，在本例中为 `⌘Ö`。

某些快捷键包含有关方向性的信息。例如，`⌘[` 可以显示上一个视图。根据用户界面的布局方向，此快捷键会自动镜像到 `⌘]`。但是，这不适用于“左对齐 `⌘{`”之类的选项，这些选项无论布局方向如何，都会保持“左对齐”。如果快捷键不应该跟随用户界面的方向，而是需要在从右到左和从左到右的方向上保持一致，则使用 [withoutMirroring](../KeyboardShortcut/Localization-swift_struct/withoutMirroring.zh-Hans.md) 可以防止系统翻转快捷键。

```swift
var body: some Commands {
    CommandMenu("Card") {
        Button("Align Left") { ... }
            .keyboardShortcut("{",
                 modifiers: .option,
                 localization: .withoutMirroring)
        Button("Align Right") { ... }
            .keyboardShortcut("}",
                 modifiers: .option,
                 localization: .withoutMirroring)
    }
}
```

最后，提供选项 [custom](../KeyboardShortcut/Localization-swift_struct/custom.zh-Hans.md) 可以禁用此快捷键的自动本地化，从而告知系统国际化处理方式有所不同。

## 创建键盘快捷键

- **keyboardShortcut(_:)**：为修改后的控件分配键盘快捷键。

- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。

- **keyboardShortcut**：此环境中按钮的触发快捷键。

- **KeyboardShortcut**：键盘快捷键描述了用户按下键盘上的组合键，以激活按钮或切换开关。

- **KeyEquivalent**：按键等效项由字母、标点符号或功能键组成，可以与一组可选的修饰键组合使用，以指定键盘快捷键。

- **EventModifiers**：您可以添加到手势中的一组修饰键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/keyboardShortcut(_:modifiers:localization:)
crawled: 2025-12-02T17:41:41Z
---

# keyboardShortcut(_:modifiers:localization:)

**Instance Method**

Defines a keyboard shortcut and assigns it to the modified control.

## Declaration

```swift
nonisolated func keyboardShortcut(_ key: KeyEquivalent, modifiers: EventModifiers = .command, localization: KeyboardShortcut.Localization) -> some View

```

## Discussion

Pressing the control’s shortcut while the control is anywhere in the frontmost window or scene, or anywhere in the macOS main menu, is equivalent to direct interaction with the control to perform its primary action.

The target of a keyboard shortcut is resolved in a leading-to-trailing, depth-first traversal of one or more view hierarchies. On macOS, the system looks in the key window first, then the main window, and then the command groups; on other platforms, the system looks in the active scene, and then the command groups.

If multiple controls are associated with the same shortcut, the first one found is used.

### Localization

Provide a `localization` value to specify how this shortcut should be localized. Given that `key` is always defined in relation to the US-English keyboard layout, it might be hard to reach on different international layouts. For example the shortcut `⌘[` works well for the US layout but is hard to reach for German users, where `[` is available by pressing `⌥5`, making users type `⌥⌘5`. The automatic keyboard shortcut remapping re-assigns the shortcut to an appropriate replacement, `⌘Ö` in this case.

Certain shortcuts carry information about directionality. For instance, `⌘[` can reveal a previous view. Following the layout direction of the UI, this shortcut will be automatically mirrored to `⌘]`. However, this does not apply to items such as “Align Left `⌘{`”, which will be “left” independently of the layout direction. When the shortcut shouldn’t follow the directionality of the UI, but rather be the same in both right-to-left and left-to-right directions, using [withoutMirroring](../KeyboardShortcut/Localization-swift_struct/withoutMirroring.zh-Hans.md) will prevent the system from flipping it.

```swift
var body: some Commands {
    CommandMenu("Card") {
        Button("Align Left") { ... }
            .keyboardShortcut("{",
                 modifiers: .option,
                 localization: .withoutMirroring)
        Button("Align Right") { ... }
            .keyboardShortcut("}",
                 modifiers: .option,
                 localization: .withoutMirroring)
    }
}
```

Lastly, providing the option [custom](../KeyboardShortcut/Localization-swift_struct/custom.zh-Hans.md) disables the automatic localization for this shortcut to tell the system that internationalization is taken care of in a different way.

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut**: The keyboard shortcut that buttons in this environment will be triggered with.
- **KeyboardShortcut**: Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.
- **KeyEquivalent**: Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.
- **EventModifiers**: A set of key modifiers that you can add to a gesture.

