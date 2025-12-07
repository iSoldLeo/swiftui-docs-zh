---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/keyboardShortcut
抓取时间： 2025-12-02T17:41:41Z
---

# 键盘快捷键

**实例属性**

在此环境中触发按钮的键盘快捷键。

## 声明

```swift
var keyboardShortcut: KeyboardShortcut? { get }
```

## 讨论

当按钮的外观取决于与其关联的快捷键时，这在按钮样式中尤其有用。例如，在 macOS 上，当按钮绑定到 Return 键时，通常会以特别强调的方式绘制。这在使用内置按钮样式时会自动实现，也可以在自定义样式中使用此环境键手动实现：

```swift
private struct MyButtonStyle: ButtonStyle {
    @Environment(\.keyboardShortcut)
    private var shortcut: KeyboardShortcut?

    func makeBody(configuration: Configuration) -> some View {
        let labelFont = Font.body
            .weight(shortcut == .defaultAction ? .bold : .regular)
        configuration.label
            .font(labelFont)
    }
}
```

如果视图或其祖先未应用键盘快捷键，则环境值将为`nil`。

## 创建键盘快捷方式

- **keyboardShortcut(_:)**：为修改后的控件指定键盘快捷键。
- **keyboardShortcut(_:modifiers:)**：定义键盘快捷键并将其分配给修改后的控件。
- **keyboardShortcut(_:modifiers:localization:)**：定义键盘快捷键并将其分配给修改后的控件。
- **KeyboardShortcut**：键盘快捷方式描述了键盘上的按键组合，用户可以按这些组合键来激活按钮或切换器。
- **KeyEquivalent**：等效键由字母、标点符号或功能键组成，可与一组可选的修改键组合，以指定键盘快捷方式。
- **EventModifiers**：可以添加到手势中的一组按键修饰符。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/keyboardShortcut
crawled: 2025-12-02T17:41:41Z
---

# keyboardShortcut

**Instance Property**

The keyboard shortcut that buttons in this environment will be triggered with.

## Declaration

```swift
var keyboardShortcut: KeyboardShortcut? { get }
```

## Discussion

This is particularly useful in button styles when a button’s appearance depends on the shortcut associated with it. On macOS, for example, when a button is bound to the Return key, it is typically drawn with a special emphasis. This happens automatically when using the built-in button styles, and can be implemented manually in custom styles using this environment key:

```swift
private struct MyButtonStyle: ButtonStyle {
    @Environment(\.keyboardShortcut)
    private var shortcut: KeyboardShortcut?

    func makeBody(configuration: Configuration) -> some View {
        let labelFont = Font.body
            .weight(shortcut == .defaultAction ? .bold : .regular)
        configuration.label
            .font(labelFont)
    }
}
```

If no keyboard shortcut has been applied to the view or its ancestor, then the environment value will be `nil`.

## Creating keyboard shortcuts

- **keyboardShortcut(_:)**: Assigns a keyboard shortcut to the modified control.
- **keyboardShortcut(_:modifiers:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **keyboardShortcut(_:modifiers:localization:)**: Defines a keyboard shortcut and assigns it to the modified control.
- **KeyboardShortcut**: Keyboard shortcuts describe combinations of keys on a keyboard that the user can press in order to activate a button or toggle.
- **KeyEquivalent**: Key equivalents consist of a letter, punctuation, or function key that can be combined with an optional set of modifier keys to specify a keyboard shortcut.
- **EventModifiers**: A set of key modifiers that you can add to a gesture.

